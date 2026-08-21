# Making Every Partner Accountable for a Digital Bank Customer

I led the partner operating model for a Southeast Asian digital bank launch. I had identified that people without formal credit histories could not be served safely if identity, data, underwriting, payments, and support were handed to separate partners with no owner for the complete customer. I worked with bank leaders, regulators, product, risk, compliance and data teams, identity and telco providers, payment networks, and distribution partners.

I completed the work during my McKinsey role from July 2014 to June 2016. The product was a new bank, but the hard design problem was a chain of delegated decisions: a channel found the customer, an identity vendor established who they were, a data provider supplied consented behavioral signals, a model assessed risk, a payment system made the account useful, and servicing and collections teams owned what happened afterward.

I made that chain one partner operating system: write the handoff contracts, translate more than 400 model features into permitted partner evidence, align four partner scorecards, bind incentives to active and safely served customers, and hold expansion behind a common risk-and-growth record. The launch reached 100,000 active customers in 90 days with approval above 40%, CAC below $10, and reported NPLs of 2.4%—results that only remain meaningful when read together.

## The launch contract followed the customer, not the org chart

For each handoff I wrote an operating contract with the same fields: permitted purpose, minimum data, consent evidence, quality threshold, response time, exception owner, customer communication, retained audit evidence, and stop condition.

The contracts covered the complete path:

**discovery → eKYC and liveness → consent → alternative-data features → underwriting → account activation → first useful payment → servicing → collections → complaint → model monitoring**

The underwriting work contained more than 400 behavioral features. I translated that model complexity into partner-operable requirements: which raw signals were allowed, how they were transformed, how fresh they had to be, what missingness meant, which party could correct them, and what evidence was retained for a disputed decision. Partners were not allowed to interpret a feature list as permission to collect everything available.

## Four partner scorecards replaced one acquisition target

### Identity partner

Success meant a person could complete identity and liveness checks with evidence that Risk and Compliance accepted. We monitored completion, manual-review rate, confirmed fraud, false rejection, response time, and unresolved exceptions. The partner could not optimize completion by weakening evidence.

### Telco and data partners

The design used consented derived signals for customers with thin credit files. The scorecard covered consent capture, provenance, field completeness, latency, stability, correction, and drift. Raw data was minimized and bound to an underwriting purpose; a distribution agreement was not a blanket data right.

### Super-app and commerce distribution

Channels were paid for customers who became active and successfully served, not registrations. The useful funnel was acquired → identity complete → approved → activated → transacting → retained, with customer-acquisition cost carried alongside approval, complaints, and credit quality.

### Payments and servicing

An approved account that could not make an everyday payment did not count as inclusion. Payment and support partners were measured on successful use, availability, failed transactions, resolution, and complaint ownership. Collections entered the design before launch so approval growth could not externalize later harm.

## The contemporaneous market evidence changed the product

World Bank evidence available during the project showed both the inclusion gap and the danger of measuring only account opening. In 2014, roughly four in five adults in Malaysia, Singapore, and Thailand had access to formal financial services, while access varied sharply elsewhere in the region. The April 2016 CPMI–World Bank report placed transaction-account adoption **and usage** at the center of financial inclusion.

That evidence is why I defined the launch result as active, served customers rather than app downloads. It also justified including payment utility, not just credit approval, in partner contracts.

FATF's 2013 guidance for mobile and internet payments supplied the risk-based principle: apply controls in proportion to observed risk instead of imposing identical friction on every customer. The approach did not relax AML/CFT accountability; it made the identity and monitoring path explicit.

## Expansion was an earned operating decision

I created one launch record for Product, Risk, Compliance, Data Science, Operations, and the partner owners. The record tracked identity quality, approval, activation, payment use, customer-acquisition cost, non-performing loans, complaints, partner incidents, and model drift.

The initial population and exposure were bounded. Expansion required the measures to remain inside agreed limits and every critical exception to have an owner. The Monetary Authority of Singapore's sandbox framework was only a consultation in June 2016, not proof that this bank entered a Singapore sandbox. I used the same bounded-experiment logic—scope, safeguards, reporting, exit, and transition—without claiming regulatory participation that the record does not establish.

## The launch outcome, with denominator discipline

| Measure | Starting point | Operating target | Reported result | What the surviving record supports |
|---|---:|---:|---:|---|
| Active customers | zero | prove real use after launch | 100,000 within 90 days | active-user count; exact activity event is not retained |
| Credit approval | below 10% | widen access without breaking loss limits | above 40% | approved/eligible applications; exact eligibility rules need recovery |
| Non-performing loans | no new-bank vintage | remain inside agreed risk appetite | 2.4% | reported NPL rate; days-past-due definition and seasoning window not retained |
| Customer-acquisition cost | no launch baseline | below $10 | below $10 | channel spend divided by acquired customers; whether “acquired” means active is not retained |

The approval movement and NPL rate must be read together. A fourfold-plus approval change with a 2.4% reported NPL was the core evidence that alternative signals could extend access without visibly abandoning credit discipline. It was not a lifetime-loss forecast: a 90-day launch cannot season a long-duration portfolio, and the source record does not preserve vintage or delinquency definition.

Likewise, 100,000 active users in 90 days establishes distribution and onboarding scale only if “active” is defined consistently. Before using the story in a diligence setting, I would recover the activation event, deduplication logic, channel denominator, and cohort retention.

## The conflict I resolved

Distribution partners wanted maximum reach, model teams wanted more signals, Compliance wanted auditable restraint, and Risk wanted enough time to observe repayment. I did not average those preferences. I tied every partner's incentive to a completed, governed customer state and made exposure growth conditional on a shared scorecard.

That was my central ownership: turning a collection of vendor and channel contracts into one bank operating model. The bank retained product and risk authority; regulators retained approval authority; specialist partners remained accountable for their controls. My role was to make the boundaries, evidence, economics, and expansion decision coherent.

### Contemporaneous research base

- [World Bank — Global Findex 2014 launch](https://www.worldbank.org/en/news/feature/2015/04/20/global-findex-2014-unveils-worlds-most-comprehensive-set-of-data-on-financial-inclusion) framed the access gap during the project period.
- [World Bank — Southeast Asia financial-access discussion, August 2015](https://www.worldbank.org/en/news/press-release/2015/08/20/access-to-financial-services-key-to-lifting-people-out-of-poverty) provides regional context without pretending ASEAN was one homogeneous market.
- [CPMI and World Bank — Payment aspects of financial inclusion, April 2016](https://www.bis.org/cpmi/publ/d144.htm) supports the emphasis on useful transaction accounts and measured usage.
- [FATF — Risk-based approach to mobile and internet payments, June 2013](https://www.fatf-gafi.org/content/dam/fatf-gafi/guidance/Guidance-RBA-NPPS.pdf.coredownload.pdf) informed the proportional identity and monitoring design.
- [MAS — Regulatory sandbox consultation, June 2016](https://www.nas.gov.sg/archivesonline/data/pdfdoc/20160606006/Media%20release%20-%20Public%20Consultation%20on%20Sandbox%20Guidelines_FINAL.pdf) is used only as a period-appropriate method for bounded testing.
