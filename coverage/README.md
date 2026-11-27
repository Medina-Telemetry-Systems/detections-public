# ATT&CK coverage

Which [MITRE ATT&CK](https://attack.mitre.org/) techniques the published rules in this repository detect, built from
the ATT&CK tags in each rule file. It covers **76 rule files** across **20 techniques**.

**[Open the coverage map in ATT&CK Navigator](https://mitre-attack.github.io/attack-navigator/#layerURL=https%3A%2F%2Fraw.githubusercontent.com%2FMedina-Telemetry-Systems%2Fdetections-public%2Fmain%2Fcoverage%2Fattack-coverage-layer.json)** (ATT&CK v20, Enterprise). Darker cells have more
rules. Hover over a technique to see which vulnerabilities it covers.

The raw layer file is [`attack-coverage-layer.json`](attack-coverage-layer.json). You can also load it into your own
Navigator instance with **Open Existing Layer**.

| Technique | Name | Rule files | Covered by |
|:--|:--|:--|:--|
| [T1190](https://attack.mitre.org/techniques/T1190/) | Exploit Public-Facing Application | 60 | [CVE-2026-102895](../cards/cve-2026-102895.md), [CVE-2026-104998](../cards/cve-2026-104998.md), [CVE-2026-106125](../cards/cve-2026-106125.md), [CVE-2026-114516](../cards/cve-2026-114516.md), [CVE-2026-116779](../cards/cve-2026-116779.md), [CVE-2026-118066](../cards/cve-2026-118066.md), [CVE-2026-119077](../cards/cve-2026-119077.md), [CVE-2026-123957](../cards/cve-2026-123957.md), [CVE-2026-123958](../cards/cve-2026-123958.md), [CVE-2026-123966](../cards/cve-2026-123966.md), [CVE-2026-124010](../cards/cve-2026-124010.md), [CVE-2026-124014](../cards/cve-2026-124014.md), [CVE-2026-124057](../cards/cve-2026-124057.md), [CVE-2026-124058](../cards/cve-2026-124058.md), [CVE-2026-124580](../cards/cve-2026-124580.md), [CVE-2026-125294](../cards/cve-2026-125294.md), [CVE-2026-126768](../cards/cve-2026-126768.md), [CVE-2026-126984](../cards/cve-2026-126984.md), [CVE-2026-127275](../cards/cve-2026-127275.md), [CVE-2026-129171](../cards/cve-2026-129171.md), [CVE-2026-129250](../cards/cve-2026-129250.md), [CVE-2026-129351](../cards/cve-2026-129351.md), [CVE-2026-129353](../cards/cve-2026-129353.md), [CVE-2026-129448](../cards/cve-2026-129448.md), [CVE-2026-129449](../cards/cve-2026-129449.md), [CVE-2026-129450](../cards/cve-2026-129450.md), [CVE-2026-129451](../cards/cve-2026-129451.md), [CVE-2026-130071](../cards/cve-2026-130071.md), [CVE-2026-130072](../cards/cve-2026-130072.md), [CVE-2026-130583](../cards/cve-2026-130583.md), [CVE-2026-130856](../cards/cve-2026-130856.md), [CVE-2026-131914](../cards/cve-2026-131914.md), [CVE-2026-132165](../cards/cve-2026-132165.md), [CVE-2026-133275](../cards/cve-2026-133275.md), [CVE-2026-133469](../cards/cve-2026-133469.md), [CVE-2026-133680](../cards/cve-2026-133680.md), [CVE-2026-133968](../cards/cve-2026-133968.md), [CVE-2026-133993](../cards/cve-2026-133993.md), [CVE-2026-134882](../cards/cve-2026-134882.md), [CVE-2026-135429](../cards/cve-2026-135429.md), [CVE-2026-136549](../cards/cve-2026-136549.md), [CVE-2026-136553](../cards/cve-2026-136553.md), [CVE-2026-137481](../cards/cve-2026-137481.md), [CVE-2026-20320](../cards/cve-2026-20320.md), [CVE-2026-61680](../cards/cve-2026-61680.md), [CVE-2026-63079](../cards/cve-2026-63079.md), [CVE-2026-67449](../cards/cve-2026-67449.md), [CVE-2026-71495](../cards/cve-2026-71495.md), [CVE-2026-77367](../cards/cve-2026-77367.md) |
| [T1505.003](https://attack.mitre.org/techniques/T1505/003/) | Server Software Component: Web Shell | 4 | [CVE-2026-104998](../cards/cve-2026-104998.md), [CVE-2026-133275](../cards/cve-2026-133275.md), [CVE-2026-135202](../cards/cve-2026-135202.md) |
| [T1078.001](https://attack.mitre.org/techniques/T1078/001/) | Valid Accounts: Default Accounts | 3 | [CVE-2026-125086](../cards/cve-2026-125086.md), [CVE-2026-129444](../cards/cve-2026-129444.md), [CVE-2026-129955](../cards/cve-2026-129955.md) |
| [T1195.002](https://attack.mitre.org/techniques/T1195/002/) | Supply Chain Compromise: Compromise Software Supply Chain | 3 | [CVE-2026-132224](../cards/cve-2026-132224.md), [CVE-2026-135202](../cards/cve-2026-135202.md) |
| [T1059](https://attack.mitre.org/techniques/T1059/) | Command and Scripting Interpreter | 2 | [CVE-2026-102895](../cards/cve-2026-102895.md), [CVE-2026-106125](../cards/cve-2026-106125.md) |
| [T1068](https://attack.mitre.org/techniques/T1068/) | Exploitation for Privilege Escalation | 2 | [CVE-2026-123039](../cards/cve-2026-123039.md), [INC Ransom](../cards/actor-incransom.md) |
| [T1098](https://attack.mitre.org/techniques/T1098/) | Account Manipulation | 2 | [CVE-2026-118066](../cards/cve-2026-118066.md), [CVE-2026-130856](../cards/cve-2026-130856.md) |
| [T1036.005](https://attack.mitre.org/techniques/T1036/005/) | Masquerading: Match Legitimate Resource Name or Location | 1 | [INC Ransom](../cards/actor-incransom.md) |
| [T1053.003](https://attack.mitre.org/techniques/T1053/003/) | Scheduled Task/Job: Cron | 1 | [CVE-2026-133469](../cards/cve-2026-133469.md) |
| [T1059.004](https://attack.mitre.org/techniques/T1059/004/) | Command and Scripting Interpreter: Unix Shell | 1 | [CVE-2026-124010](../cards/cve-2026-124010.md) |
| [T1071.001](https://attack.mitre.org/techniques/T1071/001/) | Application Layer Protocol: Web Protocols | 1 | [CVE-2026-135202](../cards/cve-2026-135202.md) |
| [T1078](https://attack.mitre.org/techniques/T1078/) | Valid Accounts | 1 | [CVE-2026-100397](../cards/cve-2026-100397.md) |
| [T1136](https://attack.mitre.org/techniques/T1136/) | Create Account | 1 | [CVE-2026-129941](../cards/cve-2026-129941.md) |
| [T1189](https://attack.mitre.org/techniques/T1189/) | Drive-by Compromise | 1 | [CVE-2026-132224](../cards/cve-2026-132224.md) |
| [T1485](https://attack.mitre.org/techniques/T1485/) | Data Destruction | 1 | [CVE-2026-135429](../cards/cve-2026-135429.md) |
| [T1486](https://attack.mitre.org/techniques/T1486/) | Data Encrypted for Impact | 1 | [INC Ransom](../cards/actor-incransom.md) |
| [T1543.003](https://attack.mitre.org/techniques/T1543/003/) | Create or Modify System Process: Windows Service | 1 | [INC Ransom](../cards/actor-incransom.md) |
| [T1552.001](https://attack.mitre.org/techniques/T1552/001/) | Unsecured Credentials: Credentials In Files | 1 | [CVE-2026-130583](../cards/cve-2026-130583.md) |
| [T1555](https://attack.mitre.org/techniques/T1555/) | Credentials from Password Stores | 1 | [INC Ransom](../cards/actor-incransom.md) |
| [T1569.002](https://attack.mitre.org/techniques/T1569/002/) | System Services: Service Execution | 1 | [INC Ransom](../cards/actor-incransom.md) |

## How to read this
- **The map shows where rules exist, not proof of detection.** All rules are `experimental`: validated against test
  samples, not yet lab-tested. See [Rule status levels](../README.md#rule-status-levels).
- **Most rules sit on Initial Access (T1190)** because each one detects exploitation of a specific vulnerability as it
  arrives. The map also shows the gap: what an attacker does after getting in (execution, persistence, lateral movement)
  is covered only by a few behavior rules so far.
- **One rule file can carry more than one technique,** for example exploitation followed by command execution.
- The map updates each time rules are published.
