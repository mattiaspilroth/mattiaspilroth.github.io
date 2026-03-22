---
title: "The SOR Framework: Implementing Structural Operational Resilience"
date: 2026-03-22
lastmod: 2026-03-22
description: "A consequence-driven engineering framework for OT security in industrial environments. Addresses the realized threat population through sequenced tier-based controls, binary completion governance, and explicit residual risk ownership."
image: "images/og-sor-framework.jpg"
---

**A consequence-driven engineering discipline for operational continuity in high-consequence industrial environments.**

## 1. The Core Thesis: Miscalibration and Realized Threats

The operational technology security industry is miscalibrated. Vendor-driven threat models dominate the discourse and produce systematic resource misallocation at standard industrial operators.

The dominant realized threats are IT-origin lateral movement, ransomware spillover, and operational decay. Virtually all documented OT impact at standard operators traces to IT targeting that crossed into OT through inadequate boundary controls, or to IT compromise that triggered precautionary OT shutdown. Catastrophic process events at regulated industrial facilities are not concealable. If OT-specific nation-state attacks were producing consequences at scale, the incident record would show it

Operational Decay is a separate and independent threat category. Software-defined dependencies do not age predictably: they expire, overflow, and fail invisibly, often without generating a signal until a process-critical moment. At current threat prevalence, operational decay is a high-probability source of OT disruption independent of adversarial activity.

Process safety engineering offers the correct organizing principle for addressing these realities. A safety-instrumented system is not designed to eliminate every conceivable hazard. It is designed to interrupt credible paths to intolerable consequences, at barriers proportionate to the consequence severity, with explicit acceptance of residual risk by a named owner. The engineer does not install five independent shutoff valves on a chlorine line because four might fail. The credible failure modes are identified, barriers are placed at the points where they interrupt realistic paths to harm, and the program stops where the cost of additional protection exceeds the risk reduction it delivers. OT security should follow exactly the same engineering logic. The question is not how many controls can be implemented. It is which controls interrupt credible paths to physical consequence, at what cost, and where the rational stopping point is.

The correct instrument to address these realities is a tier-based, sequenced investment model operationalized through the Structural Operational Resilience (SOR) Framework.

## 2. Foundational OT Prerequisites

Before any tier is assessed, two structural conditions must be verified as non-negotiable prerequisites.

1. **No OT endpoint has internet access.** OT assets do not browse the web, receive email, run office productivity software, or connect directly to any internet-facing service. Tasks requiring internet access are performed on IT-protected assets, and results are transferred into OT through controlled boundary crossings.
2. **IT protects OT, not equivalent to IT.** The IT security layer is the primary barrier against the realized threat population. This protection relationship functions only if OT is genuinely isolated from the internet.

A site unable to demonstrate both conditions is categorized as **Unclassified** (Architecturally Invalid). This is a transparent management signal requiring immediate capital and engineering intervention. An OT environment with internet-connected endpoints is not an OT environment with security gaps. It is an IT environment with industrial software installed.

Only once these prerequisites are met does a site enter the framework at Tier 0, beginning work toward Tier 1 completion.

## 3. The 7-Tier Progression Model (Axis A)

The tier model operates as a funnel. Each tier reduces the credible threat population that reaches the next. A threat that cannot cross a hardened Tier 2 boundary does not reach Tier 3. The consequence ceiling established at Tier 1 bounds the maximum impact of any failure at every tier below it. Investment priority follows the same logic: the tier that eliminates the largest population of credible threats at the lowest cost is completed first.

Priority order reflects consequence severity and architectural dependency. A higher tier cannot be reported Complete until all lower tiers are verified Complete.

Tiers 1 through 5 each define one or more zones with assets, isolation boundaries, and an attack surface. A tier is not a single monolithic zone per site. Each distinct system boundary within a tier is its own zone, assessed and completed independently. A site with multiple DCS systems has multiple Tier 3 zones. A site with multiple SIS installations has multiple Tier 1 zones. A tier is Complete at site level only when every zone within that tier is Complete. One incomplete zone leaves the tier Incomplete for the site. Tiers 6 and 7 are not zones. They are programs that operate across the tier stack and are governed by different completion logic.

* **Tier 1: Safety Instrumented Systems (SIS).** The consequence ceiling for the facility. If the SIS functions as designed, no cyber attack on any other system produces consequences beyond a controlled shutdown.
* **Tier 2: IT/OT Boundary.** The primary barrier against the realized threat population, governing all connectivity crossing between IT and OT regardless of underlying network topology. The definitive test is **Island Mode** capability: the ability to sustain safe production for a prolonged period with all IT/OT connectivity severed, accepting the temporary loss of business integration and administrative functions.
* **Tier 3: DCS and Process Control.** The systems enabling direct process manipulation capability. Each distinct DCS, PLC network, or process control system is its own zone.
* **Tier 4: Process Operational Visibility.** Infrastructure providing operators with real-time process awareness. Each distinct SCADA system, historian, or alarm management platform is its own zone.
* **Tier 5: Operational Support Infrastructure.** Foundational shared services including OT networks, shared storage, PKI, backup infrastructure, and time synchronization. Segmented where the architecture supports it.
* **Tier 6: Operational Health Monitoring.** A cross-stack program, not a zone. Deploys and activates threshold-based telemetry for all decay indicators enumerated during Tiers 1 through 5. Complete when every enumerated indicator is under active threshold alerting with a named response owner, and the monitoring infrastructure itself is subject to operational health oversight.
* **Tier 7: General Security Hygiene.** The boundary where consequence-driven investment ends and externally mandated hygiene begins. Scope is set by corporate IT framework mandates or regulatory requirements rather than by the site-specific risk model. Activities include patch cycles, vulnerability scanning, asset inventory programs, encryption at rest, and SOC integration. Most sites reach Tier 7 with remaining budget exhausted. This is the expected and correct economic outcome of a rational sequenced investment model.

## 4. Zone Protection Sequence (Axis B(i))

Applies to Tiers 1 through 5. Every zone within these tiers is matured through this fixed sequence. Interior hardening is never the starting point.

1. **Isolation verification:** The zone's assets are demonstrably separated from adjacent zones and external access paths. The architectural objective is to limit cross-zone dependencies and explicitly document what functionality is sacrificed during an isolation event. It is expected and acceptable for centralized logging, health metrics, and patch updates to break under isolation. The requirement is that the zone can safely sustain core production for a prolonged period.

2. **Recovery capability:** Logic and configurations are backed up to offline, attack-resistant storage on physically separate media. Integrity is verified through test restoration, not by confirming that backup files exist.

3. **Attack surface assessment:** Because step 1 is complete, all remaining paths crossing the isolated boundary are defined. Scope is determined by technical capability to affect the assessed zone, not by data flow direction or policy configuration. A connection is in scope if it carries or can trigger modification capacity within the zone through any chain of automated action. Human-mediated action is the scope boundary on the outbound side: a connection carrying data that a human reads and then acts upon is outside the assessed zone's attack surface, as the write action belongs to the zone the human operates from. Each in-scope path is documented with business justification, permitted protocols, and authentication requirements. Paths without current business justification are removed, not documented.

4. **Interior hardening:** Applied only where steps 1 through 3 leave a specific, credible residual risk. Interior hardening is the exception, not the default.

5. **Residual risk acceptance:** Formally signed by a named risk acceptor who understands what they are accepting. The residual risk register distinguishes three control states: **Technically Blocked** (prevented by enforced system configuration independent of human behavior; cannot be bypassed without modifying the configuration), **Technically Restricted** (limited by configuration but dependent on controlled processes; access is possible under defined conditions requiring deliberate action), and **Procedurally Controlled** (dependent on policy or human compliance with no technical enforcement). Every Procedurally Controlled item is a residual by definition, requires a named acceptor, and must be explicitly acknowledged as dependent on continued human compliance under operational pressure.

6. **Health baseline enumeration:** Identify the failure modes that would undermine the zone's isolation or recovery capability to the **Explicit Indicator Specification** standard. Pointing to a category is invalid. The standard requires four fields per indicator: the specific identity of the indicator, its current value, the defined threshold that triggers revalidation, and the named response owner.

   *Example:* "OT PKI root certificate, Site A engineering zone" is not a valid indicator specification. The valid specification is: Indicator: OT PKI root certificate, CN=SiteA-OT-RootCA. Current value: expires 2026-11-14. Threshold: 90 days prior to expiry. Response owner: OT Systems Engineer, [name].

   Monitoring activation for enumerated indicators is a Tier 6 activity, not a prerequisite for Tiers 1 through 5 completion. The obligation at this step is identification, ownership, and a defined verification schedule. The obligation to monitor automatically is fulfilled when Tier 6 is complete.

## 5. Program Governance (Axis B(ii))

Applies to Tiers 6 and 7. These tiers have no zone boundary, no attack surface to scope, and no isolation to verify. Completion logic differs accordingly.

**Tier 6** is complete when every indicator enumerated to Explicit Indicator Specification standard during Tiers 1 through 5 is covered by active threshold alerting with a named response owner, and the monitoring infrastructure itself is under operational health oversight. The coverage obligation is total: an indicator not under active alerting must be explicitly retained under a documented manual verification schedule with named ownership and justification for non-conversion. Partial coverage is Incomplete.

**Tier 7** has no equivalent completion sequence. Scope is defined by external mandate: corporate IT framework requirements, regulatory obligations, or both. The correct governance posture is a prioritized backlog with named owners, realistic timelines, and a documented rationale for sequencing decisions within the backlog. Activities within Tier 7 (patch cycles, vulnerability scanning, adversarial detection, SOC integration) are legitimate and are also the lowest-ROI activities in the framework relative to the realized threat population. Their absence allows security posture to degrade slowly. Their presence does not compensate for incomplete structural foundations in Tiers 1 through 5.

## 6. Architectural Realities vs. IT Assumptions

### Centralized Management Platforms and Weaponization

IT identity management platforms, remote monitoring tools, and endpoint management agents are frequently compromised and weaponized. The attacker uses the platform's authorized reach and execution capability without a separate payload. A shared management platform with an IT-connected control plane is a sanctioned channel that bypasses the hard IT/OT border by design. The resilience impact is identical whether the disrupting input is a malicious payload or a faulty update. OT endpoints must be managed by OT-dedicated management infrastructure. No single change or platform can be permitted to simultaneously disable multiple tiers or sites.

### Cloud Telemetry and Outbound Metrics

The belief that OT environments cannot send operational metrics to cloud platforms conflates the risk of centralized control with the risk of exported visibility. These are different risks. Outbound cloud telemetry is a permitted monitoring strategy under strict architectural constraints. The connection must be OT-initiated and strictly outbound. The platform must have zero control path capability, meaning read-only by design. It must be assessed, documented, and approved as a named Tier 2 boundary crossing. Assessment scope is determined by technical capability, not policy configuration: a telemetry platform with a control capability that is policy-disabled remains within scope until technical enforcement of the disablement is verified and documented.

### The Patching and Vulnerability Reality

In IT, unpatched vulnerabilities are an emergency. In OT, CVE exploitation requires network reachability. A genuinely isolated OT asset with no reachable attack surface has near-zero security exposure from unpatched vulnerabilities. Patching is not a scheduled operational task in OT. It is a risk-based activity executed only where the tier risk assessment identifies a specific, reachable vulnerability requiring mitigation. Applying IT patch schedules to OT is a framework import error that consumes operational resources without improving security posture for isolated assets.

### Legacy Systems

OT environments contain systems with operational lifespans of 15 to 30 years. This is the designed lifecycle of industrial control equipment, not a security deficiency. A legacy PLC or HMI operating behind a properly implemented Tier 2 boundary with no externally reachable attack surface is a managed asset, not a security liability requiring emergency replacement. Replacement is driven by operational supportability and spare parts availability. Security informs but does not drive this decision for assets behind effective boundary controls.

## 7. Framework Maturity and Applicability

The tier structure presented here is a working model, not a validated standard. It has not been tested at scale across a broad range of industrial environments. Implementation will surface edge cases: zone boundary ambiguities, architectural configurations that do not map cleanly to the tier definitions, and completion criteria that prove unworkable in specific operational contexts. Where implementation reveals structural gaps, the tier model should be revised. The priority order is derived from consequence and dependency analysis, not from field validation, and should be treated accordingly.

The priority order reflects the current realized threat population. Material changes to that population warrant reassessment of tier sequencing. The threshold is shifts in the documented incident record at standard operators, not advances in theoretical attack capability. A new class of attack that remains theoretical carries no weight in this reassessment. Documented realized impact at standard operators is the threshold.

The specific tier sequence defined here is derived from the consequence profile of high-hazard process environments: SEVESO-classified and similarly regulated facilities where the SIS is the consequence ceiling and IT-origin boundary crossing is the dominant realized threat vector. That consequence profile drives the priority ordering. Different operational contexts produce different consequence profiles and therefore different priority orderings. Discrete manufacturing, pharmaceutical OT, and utilities environments carry different consequence ceilings, different boundary architectures, and different realized threat populations. Applying this framework's logic to those contexts requires deriving the tier order from the specific consequence profile of that environment. Borrowing the SEVESO-derived sequence without that derivation is a category error.

## 8. Governance and Defensibility

Binary completion replaces percentage maturity scores as the governance instrument. Tiers are Complete or Incomplete. There is no intermediate state.

Binary completion forces one of three explicit management decisions when a tier cannot be completed: allocate resources, formally accept residual risk with a named owner, or escalate. Constraints that cannot be resolved within the current planning cycle are documented as named blockers with dated remediation plans. The only outcome not permitted is not knowing where structural exposure exists.

Organizations that build toward this standard will find that regulatory defensibility under mandates like NIS2 Article 21 is a natural consequence of the program. Structured risk identification, logical control selection sequenced by architectural dependency, and explicit risk acceptance satisfy the core requirement for appropriate and proportionate security measures. A decision to address Tier 2 before Tier 7 is not a decision to ignore regulation. It is a documented, risk-based roadmap that directly satisfies the proportionality mandate.

---

*© Mattias Pilroth. Published under CC BY 4.0. mattiaspilroth.com*