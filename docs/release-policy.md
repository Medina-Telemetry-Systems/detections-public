# Release policy

| What | Subscribers | This public repository |
|---|---|---|
| **Advisories** | Same day | Same day. We publish advisories immediately because they help everyone patch. |
| **Rules** | Every rule, the morning it is written | A hand-picked sample, normally about **30 days** later |
| **Launch exception** | | The first sample rule (CVE-2026-123966) was published at launch to show what a full rule card looks like |

## How rules are chosen for the public sample

- They're clear examples of how we work: concrete source evidence, a well-explained detection, and good test coverage.
- `test` (lab-proven) rules are preferred over `experimental` ones.
- Every rule is reviewed by a person before it is released, to subscribers or to the public.

## What is never published here

- Raw threat-intelligence data or live, non-defanged indicators
- Working exploit code or real malware. Test samples are harmless by design; see [how we test](how-we-test.md).
- Anything from a client environment
