# INC Ransom: post-access behavior on Windows (4 Sigma rules)

**Actor:** INC Ransom (GOLD IONIC; MITRE ATT&CK [G1032](https://attack.mitre.org/groups/G1032/)), a ransomware-as-a-service operation active since mid-2023. Full profile: [threat-intel-reports/actors/inc-ransom.md](https://github.com/Medina-Telemetry-Systems/threat-intel-reports/blob/main/actors/inc-ransom.md)

> **The malicious part:** what affiliates do after they get in: run tools as a service disguised as "winupd", load vulnerable drivers to kill security tools, steal Veeam backup credentials, then drop the INC-README ransom note.
> **The rules check:** four Windows log events: a "winupd" service install, a service install of one of three named drivers, a PowerShell script that reads and decrypts Veeam's credential table, and creation of an INC-README file.

**Status:** experimental (passed automated validation; not yet lab-tested)
**Rules:**
- [`rules/sigma/actor-incransom-winupd-service.yml`](../rules/sigma/actor-incransom-winupd-service.yml)
- [`rules/sigma/actor-incransom-vulnerable-driver-service.yml`](../rules/sigma/actor-incransom-vulnerable-driver-service.yml)
- [`rules/sigma/actor-incransom-veeam-credential-dump.yml`](../rules/sigma/actor-incransom-veeam-credential-dump.yml)
- [`rules/sigma/actor-incransom-ransom-note.yml`](../rules/sigma/actor-incransom-ransom-note.yml)

## What it detects and why
Most of our rules catch the first step of an intrusion: exploitation of one vulnerability. These four catch what INC Ransom
affiliates do afterwards, in order of how early they fire:
1. **`winupd` service** (Windows System log, event 7045). Affiliates have run the encryptor as a service named `winupd` and
   renamed PsExec to `winupd`, so it looks like a Windows update component. Windows has no built-in service with that name.
   The rule matches the service name, or a service program ending in `\winupd.exe`.
2. **Vulnerable-driver service** (event 7045). A custom process terminator drops `filwfp.sys`, `filnk.sys` or `fildds.sys`,
   installs it as a service, and uses it to kill security products. The rule matches a new service whose image ends in one
   of those names.
3. **Veeam credential dump** (PowerShell script block logging, event 4104). Affiliates ran a modified version of the
   open-source Veeam-Get-Creds.ps1 script as encoded PowerShell. The command line shows only the encoding, but script block
   logging records the decoded script. The rule needs both the Veeam `[dbo].[Credentials]` table and the DPAPI
   `ProtectedData]::Unprotect` call in the same script.
4. **Ransom note** (file creation). The encryptor drops `INC-README.txt` and `INC-README.html`. This fires late, once
   encryption has started, but tells responders exactly which hosts are being encrypted.

## Where the evidence came from
- **Rule 1:** MITRE ATT&CK G1032, citing Huntress (2023): the encryptor was run as a service named "winupd" through the
  Service Control Manager (event 7045), and a PsExec executable was named "winupd".
- **Rules 2–4:** Acronis Threat Research Unit, 17 June 2026,
  https://www.acronis.com/en/tru/posts/from-emerging-threat-to-top-tier-ransomware-as-a-service-the-evolution-of-inc-ransomware/
  - Rule 2: the process terminator drops `filwfp.sys`, `filnk.sys` and `fildds.sys` and installs them as a service.
  - Rule 3: the decoded script selects from `[dbo].[Credentials]` and decrypts with
    `[System.Security.Cryptography.ProtectedData]::Unprotect(...)`. It is launched as `cmd.exe /Q /c powershell.exe -e ...`.
  - Rule 4: the payload drops both `.txt` and `.html` versions of the INC-README note.
- **Context:** the Australian, Tonga and New Zealand joint advisory of 6 March 2026,
  https://www.cyber.gov.au/advisory/inc-ransom-affiliate-model-enabling-targeting-of-critical-networks

## What to do
- **Turn on the logs these rules need:** Windows System log collection (rules 1 and 2), PowerShell script block logging
  (rule 3), and file-creation events from Sysmon or your EDR (rule 4).
- **Treat rules 1–3 as urgent:** they fire before encryption, when there is still time to isolate hosts.
- **Isolate Veeam backup servers** from user networks, and rotate the credentials Veeam stores if rule 3 ever fires.
- **Turn on Microsoft's vulnerable driver blocklist** to stop driver-based attacks like the one rule 2 detects.

## False-positive notes
- **Rule 1:** a third-party service genuinely named `winupd` (none known). The look-alike `winupdate` doesn't match (tested).
- **Rule 2:** a legitimate product that ships a driver with one of these exact names. Acronis doesn't name the product the
  drivers come from, so check the file's signer if it fires. An unrelated driver install doesn't match (tested).
- **Rule 3:** backup administrators or penetration testers running the same open-source script on purpose. Any other actor
  using it also matches, which is intended. A plain query of the table, or DPAPI use without it, doesn't match (tested).
- **Rule 4:** researchers or training labs handling a copy of the note. `README.txt` and `INC-README.txt.bak` don't match (tested).

## Test evidence
Automated validation on 2026-11-16:

| Check | Result |
|---|---|
| Required metadata (all four rules) | pass |
| `sigma check`; converts to Splunk, Microsoft Sentinel (KQL) and Elastic | pass |
| Each rule fires on all of its `match*.json` samples | pass |
| Each rule stays silent on all of its `nomatch*.json` samples | pass |
| Lab test against real INC Ransom activity | not yet done |

| Rule | Samples |
|---|---|
| winupd service | [`match.json`](../tests/sigma/actor-incransom-winupd-service/match.json) (service `winupd`), [`match_image_path.json`](../tests/sigma/actor-incransom-winupd-service/match_image_path.json) (program `C:\Windows\winupd.exe`); [`nomatch.json`](../tests/sigma/actor-incransom-winupd-service/nomatch.json) (normal service), [`nomatch_lookalike.json`](../tests/sigma/actor-incransom-winupd-service/nomatch_lookalike.json) (`winupdate`), [`nomatch_state_change.json`](../tests/sigma/actor-incransom-winupd-service/nomatch_state_change.json) (event 7036, not an install) |
| vulnerable driver | [`match.json`](../tests/sigma/actor-incransom-vulnerable-driver-service/match.json) (`filwfp.sys`), [`match_fildds.json`](../tests/sigma/actor-incransom-vulnerable-driver-service/match_fildds.json) (`fildds.sys`); [`nomatch.json`](../tests/sigma/actor-incransom-vulnerable-driver-service/nomatch.json) (other driver), [`nomatch_state_change.json`](../tests/sigma/actor-incransom-vulnerable-driver-service/nomatch_state_change.json) (event 7036) |
| Veeam credential dump | [`match.json`](../tests/sigma/actor-incransom-veeam-credential-dump/match.json) (table query plus DPAPI decrypt); [`nomatch.json`](../tests/sigma/actor-incransom-veeam-credential-dump/nomatch.json) (query only), [`nomatch_dpapi_only.json`](../tests/sigma/actor-incransom-veeam-credential-dump/nomatch_dpapi_only.json) (DPAPI only) |
| ransom note | [`match.json`](../tests/sigma/actor-incransom-ransom-note/match.json) (`INC-README.txt`), [`match_html.json`](../tests/sigma/actor-incransom-ransom-note/match_html.json) (`INC-README.html`); [`nomatch.json`](../tests/sigma/actor-incransom-ransom-note/nomatch.json) (`README.txt`), [`nomatch_lookalike.json`](../tests/sigma/actor-incransom-ransom-note/nomatch_lookalike.json) (`INC-README.txt.bak`) |

The samples are single JSON log events with marker values. The script samples contain only the two strings rule 3 looks
for, not a working credential dumper.

## SIEM queries
**Generated by sigma-cli** (field names exactly as in the rules; map them to your log source):

Splunk:
```
EventID=7045 ServiceName="winupd" OR ImagePath="*\\winupd.exe"
EventID=7045 ImagePath IN ("*\\filwfp.sys", "*\\filnk.sys", "*\\fildds.sys")
ScriptBlockText="*[dbo].[Credentials]*" ScriptBlockText="*ProtectedData]::Unprotect*"
TargetFilename IN ("*\\INC-README.txt", "*\\INC-README.html")
```

## ATT&CK mapping
- **T1569.002 Service Execution** and **T1036.005 Match Legitimate Resource Name or Location** (rule 1): the encryptor runs as a service with an update-like name.
- **T1068 Exploitation for Privilege Escalation** and **T1543.003 Windows Service** (rule 2): a vulnerable driver installed as a service.
- **T1555 Credentials from Password Stores** (rule 3): credentials taken from Veeam's credential store.
- **T1486 Data Encrypted for Impact** (rule 4).

## What we're unsure about
- **Age of the indicators:** the `winupd` name comes from 2023 reporting. Newer affiliates may use other names, so rule 1 is
  the most likely to go stale.
- **Rule 2's driver names** come from one incident write-up. Other INC intrusions may use different drivers.
- **Rule 3 needs script block logging,** which is off by default on many systems.
- **Rule 4 needs file-creation logging,** and some EDRs record only the first file in a burst.
- **Field names** follow the standard Windows and Sysmon names. Map them if your SIEM renames fields.
