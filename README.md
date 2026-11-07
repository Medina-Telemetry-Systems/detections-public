<img alt="Public Detections: free sample rules and advisories from Medina Telemetry Systems" src="assets/banner.png" width="100%">


# Public Detections

Free sample detection rules and vulnerability advisories from **[Medina Telemetry Systems](https://github.com/Medina-Telemetry-Systems)**.

This repository is a **public sample** of our daily detection feed. Every rule here is the real thing: the same rule, the
same documentation and the same test evidence our subscribers receive. It is published on a delay, as a sample.

## Recently released to subscribers

<!-- feed:start -->
| Released | CVE | Issue | Formats | Severity | Status | Access |
|:--|:--|:--|:--|:--|:--|:--|
| 2026-11-07 | CVE-2026-71495 | Wanderer trail app lets anyone make the server fetch internal addresses (SSRF) | Suricata | CVSS 3.1: 10.0 Critical | experimental | Subscribers |
| 2026-11-07 | CVE-2026-19868 | SonicWall SSL-VPN lets some users skip SAML login and MFA | Advisory | CVSS 3.1: 7.5 High | advisory | [advisory](advisories/cve-2026-19868.md) |
| 2026-11-07 | CVE-2026-123966 | Tenda AC19 router heap overflow via an oversized "deviceId" in parental controls | Suricata | CVSS 3.1: 10.0 Critical | experimental | [sample](cards/cve-2026-123966.md) |
| 2026-11-07 | CVE-2026-123958 | TOTOLINK CA300-PoE buffer overflow via oversized LAN DNS or language settings | Suricata | CVSS 3.1: 9.9 Critical | experimental | Subscribers |
| 2026-11-07 | CVE-2026-123957 | TOTOLINK CA300-PoE buffer overflow via an oversized "ipStart" setting | Suricata | CVSS 3.1: 9.9 Critical | experimental | Subscribers |
| 2026-11-07 | CVE-2026-118066 | LatePoint WordPress booking plugin account takeover with "IS NOT NULL" | Sigma | CVSS 3.1: 9.1 Critical | experimental | [sample](cards/cve-2026-118066.md) |

Full list: [SUBSCRIBER-RELEASES.md](SUBSCRIBER-RELEASES.md)
<!-- feed:end -->

## What's inside

| Folder | Contents |
|---|---|
| [`advisories/`](advisories/) | Plain-English advisories for important vulnerabilities, especially ones that are actively exploited but have no published technical details yet. Published **immediately**. |
| [`rules/`](rules/) | Detection rules: `sigma/`, `suricata/`, `yara/` |
| [`cards/`](cards/) | One **rule card** per vulnerability: what the rule detects and why, the quoted source evidence, false-positive notes, test results, ATT&CK mapping, and what is still uncertain |
| [`tests/`](tests/) | The harmless test samples each rule was proven against (`match*` must alert, `nomatch*` must stay silent) |
| [`docs/`](docs/) | [How we test](docs/how-we-test.md) and our [release policy](docs/release-policy.md) |

**Start with a card.** Two samples show the range:

- [`cards/cve-2026-118066.md`](cards/cve-2026-118066.md): a **Sigma** rule for web-server logs, with ready-to-use Splunk, Microsoft Sentinel and Elastic queries
- [`cards/cve-2026-123966.md`](cards/cve-2026-123966.md): a **Suricata** network rule

## Free vs. subscription

| | This public repo | Subscription *(opening soon)* |
|---|---|---|
| Advisories | Same day | Same day |
| Rules | A hand-picked sample, about **30 days** after release | **Every** rule, the **morning** it is written |
| Rule cards and test evidence | For published samples | For every rule |
| Formats | Sample formats | Sigma, Suricata and YARA, with Sigma conversions for Splunk, Microsoft Sentinel and Elastic |
| Support and tuning for your environment | Not included | Available |

Subscriptions are opening soon. **Watch** or **star** this repository to hear first.

## Rule status levels

| Status | Meaning |
|---|---|
| `experimental` | Passed automated validation: syntax, it fires on the attack sample, and it stays silent on normal samples. Samples are built from the published advisory or proof of concept. |
| `test` | Also proven in our lab against the real vulnerable software or realistic traffic. |
| `stable` | In production use for a period without problems. |

Severity is always the **CVSS v3.1** base score from NVD.

## Using these rules

- **Sigma:** convert with [sigma-cli](https://github.com/SigmaHQ/sigma-cli) for your SIEM, or use the ready-made queries in the rule's card. Map field names to your log source.
- **Suricata:** add the `.rules` file to your rule set and reload Suricata. Rules use `$HOME_NET` and `$EXTERNAL_NET`.
- **Network rules only see clear text.** HTTPS traffic must be decrypted, or the sensor placed behind TLS termination.
- **Test in your own environment first,** especially anything marked `experimental`. Each card's false-positive notes
  say what to watch for.

## License

Rules are licensed under the [Detection Rule License (DRL) 1.1](LICENSE.md). You may use, share and modify them,
including commercially, as long as you keep the author attribution (the `MTS` prefix in alert names and the author
metadata) and a link to the source.

**Provided as-is, without warranty.** No detection rule catches every variant of an attack. Use these as one layer of
your defenses.
