# Release policy

| What | Subscribers | This public repository |
|---|---|---|
| **Advisories** | Same day | Same day. We publish advisories immediately because they help everyone patch. |
| **Rules** | Every rule, the morning it is written | A hand-picked sample, normally about **30 days** later |
| **Launch exception** | | The first samples (CVE-2026-123966, Suricata, and CVE-2026-118066, Sigma) were published at launch to show what full rule cards look like |

## Monthly public drops

Public samples are published once a month as a **GitHub Release** named for the month, for example "November 2026 public drop".
The release notes list each new sample and advisory. To be notified, choose **Watch → Custom → Releases** on this repository.

The full list of everything released to subscribers, with public samples linked, is in
[SUBSCRIBER-RELEASES.md](../SUBSCRIBER-RELEASES.md).

## How rules are chosen for the public sample

- They're clear examples of how we work: concrete source evidence, a well-explained detection, and good test coverage.
- `test` (lab-proven) rules are preferred over `experimental` ones.
- Every rule is reviewed by a person before it is released, to subscribers or to the public.

## What is never published here

- Raw threat-intelligence data or live, non-defanged indicators
- Working exploit code or real malware. Test samples are harmless by design; see [how we test](how-we-test.md).
- Anything from a client environment
