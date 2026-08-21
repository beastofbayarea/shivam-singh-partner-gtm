# Releasing regulated bank workloads through an Indonesian partner offer

Participating banks had committed more than $20 million of cloud capacity. Development and test moved; regulated production remained at zero.

During my AWS role, I assembled the partner GTM system across bank Technology/Risk, an Indonesian identity provider, implementation partners, Cloud Product/Security, Marketplace, and field sellers. I treated the gap as a blocked asset: the missing product was a defensible approval path, not more awareness.

## “Sovereignty” became five decisions

1. **Jurisdiction:** where data, logs, backups, identities, and key operations ran.
2. **Authority:** who could approve users, decrypt, suspend keys, or recover.
3. **Enforcement:** whether architecture enforced the promise.
4. **Evidence:** what auditors/regulators could inspect after normal, exceptional, and outage events.
5. **Viability:** whether the controls still met banking latency, availability, and recovery needs.

AWS [Indonesia financial-services guidance](https://aws.amazon.com/financial-services/security-compliance/compliance-center/id/) establishes the Jakarta Region and compliance context; it does not grant blanket approval. Banks and regulators retained authority.

## I chose embedded trust over distribution reach

The largest local candidate had a consumer identity footprint but required a redirect and surrendered part of the bank journey. I selected a smaller API-first trust provider.

The scorecard covered local presence, assurance, liveness/recovery, API behavior, audit proof, embedded experience, failure ownership, commercial fit, and willingness to support a multi-party offer. Selection/onboarding took three weeks because trade-offs were explicit, not because diligence disappeared.

Responsibilities were asymmetric:

- bank: policy, consent, privileged approval, recovery authorization;
- trust provider: local identity proof and embedded interface;
- implementation partner: customer landing zone and evidence;
- AWS: regional cloud controls and telemetry;
- my team: one purchasable, supportable, field-operable offer.

## The first key architecture was technically sovereign and commercially unusable

An HSM path far from the workload approached ten seconds per observed operation. Literal off-platform custody broke the interactive journey.

I convened the parties to separate **root authority** from **working cryptographic operations**. The bank retained a customer-controlled local root; short-lived working keys and an operational HSM path sat near compute; confidential computing protected data in use; daily rotation bounded exposure.

The observed operation fell below one millisecond. Payload, percentile, sample, and exact boundary are not retained, so this proves removal of a path-length bottleneck—not a universal AWS latency claim.

AWS [external key-store documentation](https://docs.aws.amazon.com/kms/latest/developerguide/keystore-external.html) explicitly notes customer control alongside the lowest throughput/highest latency among KMS key-store options and customer responsibility for distance, proxy, HSM, performance, and availability. “Customer holds keys” was a requirement, not a complete design.

## The partner proposition became a landing zone

The repeatable base covered residency, network, federation, key policy, privileged access, logs, backup, recovery, and evidence retention.

Provisioning moved from an estimated six-month bespoke plan to roughly two hours. That clock covered the base environment, not application remediation, regulatory dialogue, migration, or production release.

The package did not promise foreign access was impossible. It made inspectable who could reach what, who could authorize/revoke keys, where evidence lived, how exceptions were detected, and how recovery worked.

An early telemetry path briefly routed outside the intended boundary. Evidence exposed it; the team moved it through a regional gateway before scaling. Continuous proof became part of the offer, not a post-launch audit.

## I changed the partner economics for sellers

Marketplace transactions counted toward quota, removing the penalty for using the partner route. Broad demand generation became named-account progression:

**executive access → architecture proof → control review → partner trio → marketplace transaction → regulated workload plan**

A comparable geography retained the broad approach. Indonesia produced 78% more CIO meetings and a 3.5× lead-quality result. Pre-period balance and scoring formula are absent, so this is a useful quasi-experiment, not randomized causality.

## Approval-to-pipeline evidence

| Decision | Baseline → target → recorded result | Measurement |
|---|---|---|
| Base environment | 6-month bespoke estimate → same day → ~2 h | Infrastructure workflow only |
| Interactive key path | ~10 s → banking-compatible → <1 ms observed | Architecture test; boundary incomplete |
| Executive access | comparison market → improve → 78% more CIO meetings | Treated/comparison geography |
| Lead quality | prior index → material improvement → 3.5× | Internal score; formula absent |
| Commercial path | regulated use zero → qualified progression → $122M pipeline | CRM pipeline, not revenue |
| Stranded commitment | >$20M committed/blocked → approval-ready → >$20M eligible | Capacity mapped to cleared workload, not consumption |

Partner selection, the joint proposition, responsibility split, key-path redesign, landing-zone productization, incentive change, named-account experiment, and executive story were the choices I drove. Security/Product approved controls; partners configured them; banks/regulators approved release.

The strategic GTM achievement was to make local trust purchasable. A partner mattered not because it extended reach, but because together we could convert identity, keys, evidence, recovery, seller incentive, and customer approval into one repeatable route for regulated workloads.
