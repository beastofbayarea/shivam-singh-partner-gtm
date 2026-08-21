# Releasing Regulated Bank Workloads Through an Indonesian Partner Offer

I led a partner go-to-market program for regulated cloud adoption in Indonesia. I had identified that bank risk leaders could not approve production use unless local control over identity, keys, access, evidence, and recovery was concrete. I worked with bank technology and risk teams, a local identity provider, implementation partners, cloud product and security teams, marketplace owners, and field sellers.

This was part of my AWS role, which began in July 2024. The commercial problem was unusually expensive: participating banks had already committed more than $20 million of cloud capacity, yet regulated production use remained at zero while development and test consumption had moved ahead. I treated that gap as a blocked asset, not a generic awareness problem.

## The approval record I set out to complete

A bank's decision involved several different questions that were being collapsed into the word *sovereignty*:

1. **Jurisdiction:** where customer data, logs, backups, identities, and key operations ran.
2. **Authority:** who could approve a user, decrypt data, suspend a key, or recover a service.
3. **Technical control:** whether those decisions were enforced by architecture or merely promised in a contract.
4. **Evidence:** what an auditor or regulator could inspect after a normal event, an exception, or an outage.
5. **Service viability:** whether stronger control still met the latency, uptime, and recovery needs of a banking journey.

That decomposition mattered. AWS's Indonesia compliance guidance confirms that financial institutions may use cloud services subject to applicable requirements and points to the in-country Jakarta Region and Indonesia's data-protection regime. It does not grant blanket approval. The customer remains responsible for applying the rules to its workload and control environment.

## I chose an embedded trust partner over a reach partner

The obvious local candidate had a large consumer identity footprint, but its closed user experience would have forced banks to redirect customers and surrender part of the journey. I selected a smaller, API-first Indonesian trust provider instead.

I made the choice against a written scorecard: local operating presence, assurance level, liveness and recovery behavior, API performance, audit evidence, embedded-user experience, failure ownership, commercial fit, and willingness to support a multi-party offer. Selection and onboarding took three weeks. The speed came from making trade-offs explicit, not from waiving diligence.

I owned the complete partner offer, not a referral relationship: select the trust layer, redesign a failed key path, assign control obligations across provider and bank, productize the evidence as a repeatable landing zone, change seller incentives, and prove access with named accounts. That system made more than $20 million of stranded commitment approval-ready and created a $122 million qualified pipeline, neither of which I misstate as consumed cloud revenue.

The resulting responsibility chain was deliberately asymmetric:

- the bank owned policy, customer consent, privileged approvals, and recovery authorization;
- the trust provider supplied local identity proof and an embeddable interface;
- the implementation partner configured the bank-specific landing zone and evidence package;
- AWS supplied the regional cloud controls and service telemetry;
- my partner-GTM team joined those components into one purchasable and supportable offer.

## The first key design failed the banking journey

The first architecture kept the hardware security module too far from the workload. A round trip for a key operation approached ten seconds in the observed path. That might have satisfied a literal reading of off-platform custody, but it could not support an interactive transaction.

I convened Security, Product, the trust partner, and the bank to separate the **root of authority** from every **working cryptographic operation**. We kept the customer-controlled local root, introduced short-lived working keys, placed the operational HSM path close to the compute, and added confidential-computing protection for data in use. Daily rotation limited exposure without putting a remote ceremony in every customer request.

The observed operation fell below one millisecond. That comparison is directionally strong but not a reusable product benchmark: the retained record does not specify payload, percentile, sample size, or whether the two observations covered precisely the same operation. I therefore use it in an interview as evidence of finding and removing a path-length bottleneck, not as a universal AWS latency claim.

AWS's own KMS documentation supports the architectural trade-off. It says external key stores provide customer control over an external root of trust, but also the lowest throughput and highest latency among KMS key-store choices; distance, networking, proxy software, and the external HSM determine performance and availability. It recommends close placement and makes the customer responsible for those operating properties. That is why “customer holds the keys” was a design requirement, not a sufficient design.

## A landing zone turned the argument into a repeatable test

I converted the assurance chain into a reusable, bank-configurable landing zone covering residency, network boundaries, identity federation, key policy, privileged access, logging, backup, recovery, and evidence retention. NIST SP 800-53 Revision 5 supplied the control vocabulary; NIST CSF 2.0 helped assign outcomes across Govern, Identify, Protect, Detect, Respond, and Recover.

Provisioning the base environment fell from an estimated six-month bespoke implementation to roughly two hours. That measure is **landing-zone provisioning time**, not a claim that a regulated bank migrated a production application in two hours. Application remediation, customer acceptance, regulator engagement, and release management remained outside that clock.

The control package also avoided an indefensible promise. It did not say foreign access was impossible. It showed:

- which identities and support paths could reach which resources;
- which party could authorize or revoke a key;
- where logs and backups were retained;
- how an exception would be detected and reviewed;
- how recovery worked if the local trust service or key path failed.

When an early telemetry path briefly routed outside the intended boundary, the evidence exposed it. The team moved that path through a regional gateway before it became part of the repeatable offer. That incident strengthened the operating model because it proved the architecture needed continuous evidence, not a one-time diagram.

## I made the partner route economically usable

The technical pattern would have stalled if field sellers lost credit for using it. I worked with marketplace and sales leaders so partner transactions counted toward quota, then replaced broad demand generation with named-account progression:

**verified executive access → architecture proof → customer control review → partner trio assigned → marketplace transaction → regulated workload plan**

I compared the treated geography with a comparable market that retained the broad approach. The treated market produced 78% more CIO meetings, and lead quality rose 3.5 times. The retained notes do not preserve the exact lead-quality formula or the pre-period balance between markets, so I describe this as a useful quasi-experiment, not a randomized causal estimate.

The motion produced $122 million of qualified pipeline and made more than $20 million of committed capacity eligible for regulated production use. Pipeline is not booked revenue, and eligibility is not consumption. My contribution was removing a material approval barrier and creating a measurable path to those later outcomes.

## The decision ledger

| Question | Baseline | Design threshold | Observed result | How I measured it |
|---|---:|---:|---:|---|
| Could the bank provision an approved base environment? | Bespoke plan estimated at 6 months | Same-day repeatability | About 2 hours | Infrastructure workflow timestamps; excludes application migration and approvals |
| Could the trust design support an interactive path? | Remote key path approached 10 seconds | Banking-journey latency | Below 1 ms in the revised observation | Architecture test; percentile and exact operation not retained |
| Did named-account proof improve access? | Comparison-market meeting rate | Better than the broad motion | 78% more CIO meetings | Treated-versus-comparison geography; not randomized |
| Was seller attention better allocated? | Previous lead-quality index | Material improvement | 3.5× | Internal scoring; formula not retained |
| Was there a commercial path after proof? | Regulated production at zero | Qualified workload progression | $122M pipeline | CRM pipeline, not closed revenue |
| Did the stranded commitment become usable? | >$20M committed, regulated use blocked | Approval-ready capacity | >$20M eligible | Capacity mapped to workloads clearing the offer's control gate; not usage revenue |

## What I owned—and what I did not

I owned the partner choice, joint proposition, decision criteria, cross-company operating model, field incentive alignment, named-account experiment, and executive narrative. Security and product owners approved their controls; implementation partners delivered customer configurations; banks and their regulators retained approval authority. That boundary is important: I created the system that made approval defensible, but I did not substitute for it.

### Research used to reconstruct the work

- [AWS Financial Services Compliance Center — Indonesia](https://aws.amazon.com/financial-services/security-compliance/compliance-center/id/) establishes the Jakarta-region and regulatory context without implying automatic customer compliance.
- [AWS KMS — External key stores](https://docs.aws.amazon.com/kms/latest/developerguide/keystore-external.html) documents customer control, latency, availability, and operating-responsibility trade-offs.
- [AWS KMS — Key-store comparison](https://docs.aws.amazon.com/kms/latest/developerguide/key-store-overview.html) supports the distinction among standard, CloudHSM, and external key stores.
- [NIST SP 800-53 Revision 5](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final) and [NIST Cybersecurity Framework 2.0](https://doi.org/10.6028/NIST.CSWP.29) supplied the control and accountability language.
