<img alt="Public Detections: detection rules and advisories from Medina Telemetry Systems" src="assets/banner.png" width="100%">


# Public Detections

Detection rules and vulnerability advisories for newly disclosed and actively exploited vulnerabilities, from
**[Medina Telemetry Systems](https://github.com/Medina-Telemetry-Systems)**.

Every rule here comes with its rationale, the source evidence it is based on, false-positive notes, and test evidence
showing it fires on the attack and stays silent on normal activity. When the public information isn't concrete enough
for a reliable rule, we publish an advisory instead of guessing.

## Index

<!-- feed:start -->
**42 rules** and **26 advisories**, newest first.

| Date | CVE or actor | Issue | Type | Severity | Status | Details |
|:--|:--|:--|:--|:--|:--|:--|
| 2026-11-21 | CVE-2026-76466 | Cisco Expressway clusters let an attacker run commands as root through the database service | Advisory | CVSS 3.1: 9.8 Critical | advisory | [advisory](advisories/cve-2026-76466.md) |
| 2026-11-21 | CVE-2026-133968 | MONAI Label lets anyone write files anywhere through the datastore "image" name | Sigma, Suricata | CVSS 3.1: 9.8 Critical | experimental | [card](cards/cve-2026-133968.md) |
| 2026-11-21 | CVE-2026-133680 | D-Link DCS-935L camera command injection through the Local Recording account and password | Suricata | CVSS 3.1: 9.9 Critical | experimental | [card](cards/cve-2026-133680.md) |
| 2026-11-21 | CVE-2026-123890 | VMware vCenter authentication bypass in the Directory Service | Advisory | CVSS 3.1: 9.8 Critical | advisory | [advisory](advisories/cve-2026-123890.md) |
| 2026-11-21 | CVE-2025-42884 | SAP NetWeaver Enterprise Portal JNDI injection | Advisory | CVSS 3.1: 6.5 Medium | advisory | [advisory](advisories/cve-2025-42884.md) |
| 2026-11-20 | CVE-2026-77367 | Daptin SQL injection through the sort parameter, no login needed | Sigma | CVSS 3.1: 9.4 Critical | experimental | [card](cards/cve-2026-77367.md) |
| 2026-11-20 | CVE-2026-77312 | Flyto2 Core file-writing modules can write outside the sandbox (incomplete earlier fix) | Advisory | CVSS 3.1: 10.0 Critical | advisory | [advisory](advisories/cve-2026-77312.md) |
| 2026-11-20 | CVE-2026-133493 | D-Link DIR-600L router command injection in the UPnP event handler | Advisory | CVSS 3.1: 10.0 Critical | advisory | [advisory](advisories/cve-2026-133493.md) |
| 2026-11-20 | CVE-2026-133323 | Mitel MiCollab command injection without login in the conferencing component | Advisory | CVSS 3.1: 10.0 Critical | advisory | [advisory](advisories/cve-2026-133323.md) |
| 2026-11-20 | CVE-2026-114516 | Etherpad lets anyone read server files through encoded backslashes in /static/ | Sigma, Suricata | CVSS 3.1: 9.8 Critical | experimental | [card](cards/cve-2026-114516.md) |
| 2026-11-18 | CVE-2026-61680 | WeGIA lets anyone create charge (billing) records without logging in | Suricata | CVSS 3.1: 9.8 Critical | experimental | [card](cards/cve-2026-61680.md) |
| 2026-11-18 | CVE-2026-130856 | 53AIHub lets anyone re-run the installer and take over admin accounts | Sigma | CVSS 3.1: 9.8 Critical | experimental | [card](cards/cve-2026-130856.md) |
| 2026-11-18 | CVE-2026-130583 | Rootways Authorize.net CIM Pro (Magento 2) Apple Pay SSRF reads store secrets | Sigma, Suricata | CVSS 3.1: 9.3 Critical | experimental | [card](cards/cve-2026-130583.md) |
| 2026-11-18 | CVE-2026-115731 | Puppet Server runs attacker code from a crafted agent report | Advisory | CVSS 3.1: 9.9 Critical | advisory | [advisory](advisories/cve-2026-115731.md) |
| 2026-11-18 | CVE-2026-100397 | Rucio accepts SSH challenge nonces as login tokens (log in as any account, including root) | Suricata | CVSS 3.1: 10.0 Critical | experimental | [card](cards/cve-2026-100397.md) |
| 2026-11-17 | CVE-2026-130072 | Cloud Commander unauthenticated file rename with path traversal | Suricata | CVSS 3.1: 9.1 Critical | experimental | [card](cards/cve-2026-130072.md) |
| 2026-11-17 | CVE-2026-130071 | go1cms lets anyone edit any record, including user accounts | Suricata | CVSS 3.1: 9.8 Critical | experimental | [card](cards/cve-2026-130071.md) |
| 2026-11-17 | CVE-2026-129955 | NodePress admin login works with the built-in default password "root" | Suricata | CVSS 3.1: 9.8 Critical | experimental | [card](cards/cve-2026-129955.md) |
| 2026-11-17 | CVE-2026-129941 | Prime CMS lets anyone register an admin account through GraphQL | Suricata | CVSS 3.1: 9.8 Critical | experimental | [card](cards/cve-2026-129941.md) |
| 2026-11-17 | CVE-2026-129448 | Apache Roller XML-RPC deserializes attacker objects before login | Suricata | CVSS 3.1: 9.8 Critical | experimental | [card](cards/cve-2026-129448.md) |
| 2026-11-16 | INC Ransom | post-access behavior on Windows (4 Sigma rules) | Sigma | Behavior rule (no CVSS) | experimental | [card](cards/actor-incransom.md) |
| 2026-11-16 | CVE-2026-129483 | Cyrus SASL's SRP mechanism lets anyone log in as any user without the password | Advisory | CVSS 3.1: 9.1 Critical | advisory | [advisory](advisories/cve-2026-129483.md) |
| 2026-11-16 | CVE-2026-129451 | DrayTek Vigor2960 path traversal in the guest-list export name lets an admin write and delete files as root | Suricata | CVSS 3.1: 9.9 Critical | experimental | [card](cards/cve-2026-129451.md) |
| 2026-11-16 | CVE-2026-129450 | DrayTek Vigor2960 path traversal in the web-backup archive name lets an admin write and delete files as root | Suricata | CVSS 3.1: 9.9 Critical | experimental | [card](cards/cve-2026-129450.md) |
| 2026-11-16 | CVE-2026-125769 | Advanced Form Integration (WordPress) privilege escalation to administrator | Advisory | CVSS 3.1: 9.8 Critical | advisory | [advisory](advisories/cve-2026-125769.md) |
| 2026-11-16 | CVE-2026-122662 | Document Library Pro (WordPress) PHP object injection without login | Advisory | CVSS 3.1: 9.8 Critical | advisory | [advisory](advisories/cve-2026-122662.md) |
| 2026-11-15 | CVE-2026-129449 | DrayTek Vigor2960 command injection through a multipart field name in the switch-config upload | Suricata | CVSS 3.1: 9.9 Critical | experimental | [card](cards/cve-2026-129449.md) |
| 2026-11-15 | CVE-2026-129444 | D-Link DSL-6740C modem ships a hard-coded FTP account with full access | Suricata | CVSS 3.1: 10.0 Critical | experimental | [card](cards/cve-2026-129444.md) |
| 2026-11-15 | CVE-2026-129353 | D-Link DIR-600L login page stack overflow from an oversized "id" or "password", before login | Suricata | CVSS 3.1: 10.0 Critical | experimental | [card](cards/cve-2026-129353.md) |
| 2026-11-15 | CVE-2026-129351 | TRENDnet TEW-657BRM router web server overflow from an oversized ".htm" request, before login | Suricata | CVSS 3.1: 10.0 Critical | experimental | [card](cards/cve-2026-129351.md) |
| 2026-11-15 | CVE-2026-129250 | Edimax BR6478ACV2 router buffer overflow from an oversized PPTP user name | Suricata | CVSS 3.1: 9.9 Critical | experimental | [card](cards/cve-2026-129250.md) |
| 2026-11-14 | CVE-2026-63079 | RBH Integra32 access-control server runs attacker code as SYSTEM through its old .NET Remoting port | Suricata | CVSS 3.1: 9.8 Critical | experimental | [card](cards/cve-2026-63079.md) |
| 2026-11-14 | CVE-2026-129171 | NginxPulse log dashboard lets anyone run SQL through its stats API (no login) | Sigma, Suricata | CVSS 3.1: 9.8 Critical | experimental | [card](cards/cve-2026-129171.md) |
| 2026-11-14 | CVE-2026-126173 | AutomatorWP Webhooks lets anyone reset a WordPress admin's password (specific setup only) | Advisory | CVSS 3.1: 9.8 Critical | advisory | [advisory](advisories/cve-2026-126173.md) |
| 2026-11-14 | CVE-2026-123039 | Check Point Gaia DynamicCLI daemon runs any local user's command as root | Sigma | CVSS 3.1: 7.8 High | experimental | [card](cards/cve-2026-123039.md) |
| 2026-11-14 | CVE-2026-114713 | UnrealIRCd lets any ordinary user inject server-to-server commands on linked networks | Advisory | CVSS 3.1: 8.6 High | advisory | [advisory](advisories/cve-2026-114713.md) |
| 2026-11-13 | CVE-2026-127275 | Linksys EA8100 router lets anyone on the network change two settings without logging in | Suricata | CVSS 3.1: 10.0 Critical | experimental | [card](cards/cve-2026-127275.md) |
| 2026-11-13 | CVE-2026-126378 | Vvveb CMS lets an admin upload a PHP web shell inside a theme ZIP (nginx deployments) | Advisory | CVSS 3.1: 9.1 Critical | advisory | [advisory](advisories/cve-2026-126378.md) |
| 2026-11-13 | CVE-2026-124014 | Copeland XWEB EVO refrigeration controller lets anyone overwrite its system configuration | Suricata | CVSS 3.1: 9.1 Critical | experimental | [card](cards/cve-2026-124014.md) |
| 2026-11-13 | CVE-2026-124010 | Copeland XWEB EVO refrigeration controller runs any command as root from one web request | Sigma, Suricata | CVSS 3.1: 9.8 Critical | experimental | [card](cards/cve-2026-124010.md) |
| 2026-11-13 | CVE-2026-119077 | ELEX WordPress HelpDesk plugin runs attacker code through a serialized object in a ticket label | Suricata | CVSS 3.1: 9.8 Critical | experimental | [card](cards/cve-2026-119077.md) |
| 2026-11-12 | CVE-2026-67449 | Portabase lets anyone overwrite its master encryption key through an upload header | Suricata | CVSS 3.1: 9.8 Critical | experimental | [card](cards/cve-2026-67449.md) |
| 2026-11-12 | CVE-2026-126768 | OpsTree REMS lets anyone log in as admin by setting an "is_local_auth" flag | Suricata | CVSS 3.1: 9.8 Critical | experimental | [card](cards/cve-2026-126768.md) |
| 2026-11-12 | CVE-2026-126259 | FortiOS high-availability clusters can be taken over with crafted HA packets | Advisory | CVSS 3.1: 9.8 Critical | advisory | [advisory](advisories/cve-2026-126259.md) |
| 2026-11-12 | CVE-2026-124814 | Ultimate Addons for Elementor Forms (WordPress) lets anyone upload a PHP file and take over the site | Advisory | CVSS 3.1: 9.8 Critical | advisory | [advisory](advisories/cve-2026-124814.md) |
| 2026-11-12 | CVE-2026-110697 | Red Hat Quay leaks other tenants' robot-account tokens through an underscore in a namespace name | Advisory | CVSS 3.1: 9.9 Critical | advisory | [advisory](advisories/cve-2026-110697.md) |
| 2026-11-11 | CVE-2026-20320 | Cisco BroadWorks reads attacker-chosen files through XML external entities in OCI-P messages | Suricata | CVSS 3.1: 7.5 High | experimental | [card](cards/cve-2026-20320.md) |
| 2026-11-11 | CVE-2026-125350 | Chrome and other Chromium browsers can run attacker code from a crafted web page (XML use-after-free) | Advisory | CVSS 3.1: 8.8 High | advisory | [advisory](advisories/cve-2026-125350.md) |
| 2026-11-11 | CVE-2026-124194 | Microsoft Outlook spoofing because a risky action happens without warning the user | Advisory | CVSS 3.1: 6.5 Medium | advisory | [advisory](advisories/cve-2026-124194.md) |
| 2026-11-11 | CVE-2026-116606 | Barracuda Email Security Gateway lets anyone with access to the admin interface import a configuration without logging in | Advisory | CVSS 3.1: not yet scored | advisory | [advisory](advisories/cve-2026-116606.md) |
| 2026-11-11 | CVE-2026-111560 | Barracuda appliances run attacker commands as root through the timezone setting | Advisory | CVSS 3.1: not yet scored | advisory | [advisory](advisories/cve-2026-111560.md) |
| 2026-11-10 | CVE-2026-125086 | D-Link M60 mesh router's MQTT broker accepts a hard-coded admin/admin login | Suricata | CVSS 3.1: 10.0 Critical | experimental | [card](cards/cve-2026-125086.md) |
| 2026-11-10 | CVE-2026-123218 | IBM Aspera Faspex lets a logged-in user become a full administrator | Advisory | CVSS 3.1: 9.8 Critical | advisory | [advisory](advisories/cve-2026-123218.md) |
| 2026-11-10 | CVE-2026-123158 | OpenSSH password login bypass ("SSHole") on some Linux systems built without PAM | Advisory | CVSS 3.1: 8.1 High | advisory | [advisory](advisories/cve-2026-123158.md) |
| 2026-11-10 | CVE-2026-116779 | FreeSWITCH runs API commands sent in a SIP chat MESSAGE addressed to "api+" | Suricata | CVSS 3.1: 9.8 Critical | experimental | [card](cards/cve-2026-116779.md) |
| 2026-11-10 | CVE-2026-102895 | GPUStack grants admin to anyone whose request looks like it came from localhost | Sigma, Suricata | CVSS 3.1: 9.8 Critical | experimental | [card](cards/cve-2026-102895.md) |
| 2026-11-09 | CVE-2026-124580 | Feiyuxing VW2100 / VEC10GP command injection via the WeChat Wi-Fi login "extend" value | Suricata | CVSS 3.1: 10.0 Critical | experimental | [card](cards/cve-2026-124580.md) |
| 2026-11-09 | CVE-2026-124560 | D-Link DIR-878 router heap overflow via the "uid" value in the CAPTCHA settings call | Advisory | CVSS 3.1: 9.8 Critical | advisory | [advisory](advisories/cve-2026-124560.md) |
| 2026-11-08 | CVE-2026-124058 | TOTOLINK CA300-PoE buffer overflow via an oversized "ApCliKeyStr" repeater password | Suricata | CVSS 3.1: 9.1 Critical | experimental | [card](cards/cve-2026-124058.md) |
| 2026-11-08 | CVE-2026-124057 | TOTOLINK CA300-PoE buffer overflow via an oversized "Key1Str1" Wi-Fi key | Suricata | CVSS 3.1: 9.1 Critical | experimental | [card](cards/cve-2026-124057.md) |
| 2026-11-08 | CVE-2026-123614 | imgproxy heap overflow from an ICO image that lies about its size | Advisory | CVSS 3.1: 9.8 Critical | advisory | [advisory](advisories/cve-2026-123614.md) |
| 2026-11-08 | CVE-2026-122041 | Checkout Field Editor for WooCommerce (Pro) lets anyone delete site media files | Advisory | CVSS 3.1: 9.1 Critical | advisory | [advisory](advisories/cve-2026-122041.md) |
| 2026-11-07 | CVE-2026-71495 | Wanderer trail app lets anyone make the server fetch internal addresses (SSRF) | Suricata | CVSS 3.1: 10.0 Critical | experimental | [card](cards/cve-2026-71495.md) |
| 2026-11-07 | CVE-2026-19868 | SonicWall SSL-VPN lets some users skip SAML login and MFA | Advisory | CVSS 3.1: 7.5 High | advisory | [advisory](advisories/cve-2026-19868.md) |
| 2026-11-07 | CVE-2026-123966 | Tenda AC19 router heap overflow via an oversized "deviceId" in parental controls | Suricata | CVSS 3.1: 10.0 Critical | experimental | [card](cards/cve-2026-123966.md) |
| 2026-11-07 | CVE-2026-123958 | TOTOLINK CA300-PoE buffer overflow via oversized LAN DNS or language settings | Suricata | CVSS 3.1: 9.9 Critical | experimental | [card](cards/cve-2026-123958.md) |
| 2026-11-07 | CVE-2026-123957 | TOTOLINK CA300-PoE buffer overflow via an oversized "ipStart" setting | Suricata | CVSS 3.1: 9.9 Critical | experimental | [card](cards/cve-2026-123957.md) |
| 2026-11-07 | CVE-2026-118066 | LatePoint WordPress booking plugin account takeover with "IS NOT NULL" | Sigma | CVSS 3.1: 9.1 Critical | experimental | [card](cards/cve-2026-118066.md) |
<!-- feed:end -->

## What's inside

| Folder | Contents |
|---|---|
| [`advisories/`](advisories/) | Plain-English advisories for important vulnerabilities, especially ones that are actively exploited but have no published technical details yet |
| [`rules/`](rules/) | Detection rules: `sigma/`, `suricata/`, `yara/` |
| [`cards/`](cards/) | One **rule card** per vulnerability or threat actor: what the rule detects and why, the quoted source evidence, false-positive notes, test results, ATT&CK mapping, and what is still uncertain |
| [`tests/`](tests/) | The harmless test samples each rule was proven against (`match*` must alert, `nomatch*` must stay silent) |
| [`coverage/`](coverage/) | The [ATT&CK coverage map](coverage/README.md): which MITRE ATT&CK techniques the rules cover, as a table and an ATT&CK Navigator layer |
| [`docs/`](docs/) | [How we test](docs/how-we-test.md) and our [publishing policy](docs/release-policy.md) |

**Start with a card.** Two examples show the range:

- [`cards/cve-2026-118066.md`](cards/cve-2026-118066.md): a **Sigma** rule for web-server logs, with ready-to-use Splunk, Microsoft Sentinel and Elastic queries
- [`cards/cve-2026-123966.md`](cards/cve-2026-123966.md): a **Suricata** network rule

## Rule status levels

| Status | Meaning |
|---|---|
| `experimental` | Passed automated validation: syntax, it fires on the attack sample, and it stays silent on normal samples. Samples are built from the published advisory or proof of concept. |
| `test` | Also proven in a lab against the real vulnerable software or realistic traffic. |
| `stable` | In use for a period without problems. |

Severity is always the **CVSS v3.1** base score from NVD.

## Using these rules

- **Sigma:** convert with [sigma-cli](https://github.com/SigmaHQ/sigma-cli) for your SIEM, or use the ready-made queries in the rule's card. Map field names to your log source.
- **Suricata:** add the `.rules` file to your rule set and reload Suricata. Rules use `$HOME_NET` and `$EXTERNAL_NET`.
- **Network rules only see clear text.** HTTPS traffic must be decrypted, or the sensor placed behind TLS termination.
- **Test in your own environment first,** especially anything marked `experimental`. Each card's false-positive notes
  say what to watch for.

Feedback is welcome. If a rule misses a variant or fires on normal traffic, please open an issue.

## License

Rules are licensed under the [Detection Rule License (DRL) 1.1](LICENSE.md). You may use, share and modify them,
including commercially, as long as you keep the author attribution (the `MTS` prefix in alert names and the author
metadata) and a link to the source.

**Provided as-is, without warranty.** No detection rule catches every variant of an attack. Use these as one layer of
your defenses.
