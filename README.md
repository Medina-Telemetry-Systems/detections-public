<img alt="Public Detections: detection rules and advisories from Medina Telemetry Systems" src="assets/banner.png" width="100%">


# Public Detections

Detection rules and vulnerability advisories for newly disclosed and actively exploited vulnerabilities, from
**[Medina Telemetry Systems](https://github.com/Medina-Telemetry-Systems)**.

Every rule here comes with its rationale, the source evidence it is based on, false-positive notes, and test evidence
showing it fires on the attack and stays silent on normal activity. When the public information isn't concrete enough
for a reliable rule, we publish an advisory instead of guessing.

## Index

<!-- feed:start -->
**2 rules** and **3 advisories**, newest first.

| Date | CVE | Issue | Type | Severity | Status | Details |
|:--|:--|:--|:--|:--|:--|:--|
| 2026-11-08 | CVE-2026-123614 | imgproxy heap overflow from an ICO image that lies about its size | Advisory | CVSS 3.1: 9.8 Critical | advisory | [advisory](advisories/cve-2026-123614.md) |
| 2026-11-08 | CVE-2026-122041 | Checkout Field Editor for WooCommerce (Pro) lets anyone delete site media files | Advisory | CVSS 3.1: 9.1 Critical | advisory | [advisory](advisories/cve-2026-122041.md) |
| 2026-11-07 | CVE-2026-19868 | SonicWall SSL-VPN lets some users skip SAML login and MFA | Advisory | CVSS 3.1: 7.5 High | advisory | [advisory](advisories/cve-2026-19868.md) |
| 2026-11-07 | CVE-2026-123966 | Tenda AC19 router heap overflow via an oversized "deviceId" in parental controls | Suricata | CVSS 3.1: 10.0 Critical | experimental | [card](cards/cve-2026-123966.md) |
| 2026-11-07 | CVE-2026-118066 | LatePoint WordPress booking plugin account takeover with "IS NOT NULL" | Sigma | CVSS 3.1: 9.1 Critical | experimental | [card](cards/cve-2026-118066.md) |
<!-- feed:end -->

## What's inside

| Folder | Contents |
|---|---|
| [`advisories/`](advisories/) | Plain-English advisories for important vulnerabilities, especially ones that are actively exploited but have no published technical details yet |
| [`rules/`](rules/) | Detection rules: `sigma/`, `suricata/`, `yara/` |
| [`cards/`](cards/) | One **rule card** per vulnerability: what the rule detects and why, the quoted source evidence, false-positive notes, test results, ATT&CK mapping, and what is still uncertain |
| [`tests/`](tests/) | The harmless test samples each rule was proven against (`match*` must alert, `nomatch*` must stay silent) |
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
