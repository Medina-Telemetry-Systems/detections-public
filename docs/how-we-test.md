# How we test

A rule can pass every syntax check and still **detect nothing**, or fire all day on normal traffic. Our process is built
to catch both problems before a rule is published.

## 1. A rule needs concrete evidence

We only write a rule when the source gives us something **specific** to match: an exact request path and parameter, a
string, a process or command line, or a documented log message. It must come from a vendor advisory, a patch, or a
public proof of concept.

If there's nothing concrete, for example an exploited vulnerability whose vendor hasn't published details, we write an
**advisory** instead of guessing.

## 2. The rule goes where the evidence is visible

| Format | Used when the evidence appears in… |
|---|---|
| **Sigma** | Log fields that systems actually record: URL path and query, user agent, process creation, authentication events |
| **Suricata** | Network traffic, including request bodies, which web-server logs do *not* record |
| **YARA** | A real file artifact, such as a web shell or payload, with known strings |

## 3. Every rule must prove itself on samples

Each rule ships with test samples in `tests/<format>/<rule-id>/`:

- **`match*` samples:** the attack as described by the source. The rule **must alert** on every one.
- **`nomatch*` samples:** normal use, plus deliberately tricky near-misses, such as a legitimately long value or
  look-alike numbers in the wrong place. The rule **must stay silent** on every one.

Our validation runs the real tools on every rule:

| Format | Checks |
|---|---|
| Sigma | `sigma check`; conversion to Splunk, Microsoft Sentinel (KQL) and Elastic; behaviour test against sample log events |
| Suricata | Suricata's rule test mode (`-T`); replay of every sample capture; every signature must fire at least once |
| YARA | Compile; scan of every sample file |

The results are written into the rule's card **by the tools themselves**, in the "Test evidence" table. A rule that
fails any check is **quarantined** and never released.

## 4. Samples are harmless by design

Test samples contain only what is needed to trigger the detection, such as padding characters, marker strings or
ordinary requests. They never contain working exploit code, shellcode or malware.

## 5. AI-assisted drafting, human review

Rules, cards and advisories are drafted with the help of an AI assistant (Anthropic's Claude), working from the sources
cited in each card. The AI's draft is not trusted on its own: every rule must pass the automated checks above, and a
person reviews it before it is published.

Before publication, the reviewer checks each rule card:

- Does the source really say what the card quotes?
- Is the rule aimed at the harmful part of the attack?
- Would normal use trigger it?
- Is anything in "What I'm unsure about" a deal-breaker?

## 6. Lab proof

Rules start as `experimental`. They're promoted to `test` once they have been proven in a lab against the real
vulnerable software or realistic traffic. The lab, an isolated network with Suricata and Wazuh, is being built. Until
it is in use, every rule here is `experimental`.

## Severity

We always report the **CVSS v3.1** base score from NVD. Actively exploited vulnerabilities from CISA's KEV catalog are
prioritized whatever their score.
