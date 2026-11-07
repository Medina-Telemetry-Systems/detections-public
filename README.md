# Medina Telemetry Systems: Public Detections

Free sample detection rules and vulnerability advisories from **Medina Telemetry Systems**.

This repository is a **public sample** of our daily detection feed. Every rule here is the real thing: the same rule, the
same documentation and the same test evidence our subscribers receive. It is published on a delay, as a sample.

## What's inside

| Folder | Contents |
|---|---|
| [`advisories/`](advisories/) | Plain-English advisories for important vulnerabilities, especially ones that are actively exploited but have no published technical details yet. Published **immediately**. |
| [`rules/`](rules/) | Detection rules: `sigma/`, `suricata/`, `yara/` |
| [`cards/`](cards/) | One **rule card** per vulnerability: what the rule detects and why, the quoted source evidence, false-positive notes, test results, ATT&CK mapping, and what is still uncertain |
| [`tests/`](tests/) | The harmless test samples each rule was proven against (`match*` must alert, `nomatch*` must stay silent) |
| [`docs/`](docs/) | [How we test](docs/how-we-test.md) and our [release policy](docs/release-policy.md) |

**Start with a card.** For example, [`cards/cve-2026-123966.md`](cards/cve-2026-123966.md).

## Free vs. subscription

| | This public repo | Subscription *(opening soon)* |
|---|---|---|
| Advisories | ✔ same day | ✔ same day |
| Rules | A hand-picked sample, about **30 days** after release | **Every** rule, the **morning** it is written |
| Rule cards and test evidence | ✔ for published samples | ✔ for every rule |
| Formats | Sample formats | Sigma, Suricata and YARA, with Sigma conversions for Splunk, Microsoft Sentinel and Elastic |
| Support and tuning for your environment | — | Available |

Subscriptions are opening soon. **Watch** or **star** this repository to hear first.

## Rule status levels

| Status | Meaning |
|---|---|
| `experimental` | Passed automated validation: syntax, it fires on the attack sample, and it stays silent on normal samples. Samples are built from the published advisory or proof of concept. |
| `test` | Also proven in our lab against the real vulnerable software or realistic traffic. |
| `stable` | In production use for a period without problems. |

Severity is always the **CVSS v3.1** base score from NVD.

## Using these rules

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
