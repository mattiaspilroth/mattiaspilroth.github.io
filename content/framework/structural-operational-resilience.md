---
title: "The SOR Framework: Implementing Structural Operational Resilience"
date: 2026-03-22
lastmod: 2026-03-24
description: "A consequence-driven engineering framework for OT security in industrial environments. Addresses the realized threat population through sequenced tier-based controls, binary completion governance, and explicit residual risk ownership."
image: "images/og-sor-framework.jpg"
---

**A consequence-driven engineering discipline for operational continuity in high-consequence industrial environments.**

## 1. The Problem: Coverage Without Resilience

OT security programs at standard operators (sites outside the narrow band of strategically targeted national infrastructure) are organized around coverage. Coverage is measurable, auditable, and procurable. What it does not measure is whether the controls address the conditions under which these environments actually fail.

The frameworks driving most OT security programs were built for environments with different failure cost structures, different change tolerances, and different threat populations. They produce programs calibrated to demonstrate control presence across the estate rather than to concentrate protection where consequence is highest. The assume-everywhere posture that makes those frameworks internally consistent for IT produces an unbounded catalog with no stopping point derived from consequence or cost. Under fixed operational budgets, the result is predictable: resources spread across the full control surface while the structural conditions that determine whether the environment can withstand disruption remain unaddressed.

Process safety engineering offers the correct organizing principle. A safety-instrumented system is not designed to eliminate every conceivable hazard. It is designed to interrupt credible paths to intolerable consequences, at barriers proportionate to the consequence severity, with explicit acceptance of residual risk by a named owner. The credible failure modes are identified, barriers are placed where they interrupt realistic paths to harm, and the program stops where the cost of additional protection exceeds the risk reduction it delivers. OT security investment follows the same logic. The question is not how many controls can be implemented. It is which controls interrupt credible paths to operational consequence, at what cost, and where the rational stopping point is.

The correct instrument is a tier-based, sequenced investment model operationalized through the Structural Operational Resilience (SOR) Framework.

## 2. The Threat Model: Two Tracks

Realized OT disruption at standard operators traces predominantly to three sources: IT-origin intrusion crossing inadequate boundary controls, IT compromise triggering precautionary shutdown, and operational decay. None of these requires OT-specific attack capability. The process environment is typically collateral, not target. Disruption is produced by architectural proximity, not by adversary capability directed at OT systems.

OT-specific attack capability is documented and real. The gap between demonstrated capability and realized impact at standard operators has remained wide. That capability requires intimate, site-specific knowledge that does not transfer between targets. Development cost is high, reuse is low, and the intelligence requirement is substantial. The cost structure concentrates this capability in state-sponsored operations against strategic infrastructure, not in the threat population facing standard operators.

The framework tracks two risk trajectories concurrently.

**Track one: operational decay.** The current dominant source of OT disruption at standard operators. Long-lifecycle OT environments produce decay structurally: capital projects deliver systems at commissioning, operations inherits them funded to keep them running, and no organizational mechanism continuously verifies that documented state matches operational state. Software-defined dependencies do not age predictably. They expire, overflow, and fail invisibly, often without generating a signal until a process-critical moment. At current threat prevalence, decay is a higher-probability source of OT disruption than adversarial attack.

**Track two: attack surface expansion.** As OT environments accumulate IT components, the boundary argument that currently protects standard operators weakens. The gap between OT-specific attack capability and realized impact will not remain wide indefinitely as targets become more accessible. Each IT dependency added to an OT environment is a potential boundary concern, a potential propagation vector, and a potential interior hardening gap.

Both tracks are addressed within the same sequenced structure. Proper tier isolation with verified recovery capability is resilient against decay and adversarial threat simultaneously. The framework does not bifurcate.

The framework carries a standing review obligation. The threat balance shifts as OT environments accumulate IT components and as the incident record evolves. If the documented incident record at standard operators shows the balance between the two tracks shifting materially, the prioritization logic must shift with it. Theoretical capability advances carry no weight. Documented realized impact at standard operators is the threshold. NIS2 incident reporting obligations will progressively improve the evidence base this review obligation draws on, strengthening the case for grounding investment logic in documented incidents rather than theoretical capability.

## 3. Foundational OT Prerequisites

Before any tier is assessed, two structural conditions must be verified as non-negotiable prerequisites.

1. **No OT endpoint has internet access.** OT assets do not browse the web, receive email, run office productivity software, or connect directly to any internet-facing service. Tasks requiring internet access are performed on IT-protected assets, and results are transferred into OT through controlled boundary crossings.
2. **IT protects OT.** The IT security layer (endpoint detection, email filtering, network monitoring, incident response) is the primary barrier against the realized threat population. This protection relationship functions only if OT is genuinely isolated from the internet.

A site unable to demonstrate both conditions is categorized as **Unclassified** (Architecturally Invalid). This is a transparent management signal requiring immediate capital and engineering intervention. An OT environment with internet-connected endpoints is not an OT environment with security gaps. It is an IT environment with industrial software installed.

## 4. IT Security as OT Protection

Every unit of resource spent on effective IT endpoint detection, email security, network monitoring, and incident response reduces the threat that reaches the OT boundary. The IT layer is where the dominant realized threat enters. IT security investment has direct OT protection value that does not appear on OT security budgets and is not counted in OT security metrics, which distorts both the perceived gap and the proposed solution.

IT security maturity is a prerequisite for OT security return on investment. An organization with immature IT security that invests in deep OT instrumentation and OT-specific detection capability is addressing the wrong layer. The framework's tier sequence assumes a functioning IT security layer. Where it is not functioning, the most effective action for OT risk reduction is IT security improvement, not OT security spending.

## 5. The Investment Model

OT security investment competes within a fixed operational envelope at every standard operator. The production process is the revenue-generating asset. The funding ceiling is set by operational economics, not by security requirements, and it is real.

The tier model is a prioritization instrument for constrained environments, not an aspirational maturity checklist. A site that completes lower tiers within its operational budget is in a better security posture than a site that spent the same budget on higher-tier activities without completing structural foundations. Most sites will stall before completing the full tier stack. This is the predicted and correct economic outcome of a rational sequenced investment model applied within a fixed envelope. The sequence ensures that when a site exhausts its security capacity, it stalls in a consequence-prioritized state rather than an arbitrary one.

## 6. The 7-Tier Progression Model (Axis A)

The tier model operates as a funnel. Each tier reduces the credible threat population that reaches the next. A threat that cannot cross a hardened Tier 2 boundary does not reach Tier 3. The consequence ceiling established at Tier 1 bounds the maximum impact of any failure at every tier below it. Investment priority follows the same logic: the tier that eliminates the largest population of credible threats at the lowest cost is completed first.

Priority order reflects consequence severity and architectural dependency. A higher tier cannot be reported Complete until all lower tiers are verified Complete.

Tiers 1 through 5 each define one or more zones with assets, isolation boundaries, and an attack surface. A tier is not a single monolithic zone per site. Each distinct system boundary within a tier is its own zone, assessed and completed independently. A site with multiple DCS systems has multiple Tier 3 zones. A site with multiple SIS installations has multiple Tier 1 zones. A tier is Complete at site level only when every zone within that tier is Complete. One incomplete zone leaves the tier Incomplete for the site. Tiers 6 and 7 are not zones. They are programs that operate across the tier stack and are governed by different completion logic.

* **Tier 1: Safety Instrumented Systems (SIS).** The consequence ceiling for the facility. If the SIS functions as designed under IEC 61511 requirements, no cyber attack on any other system produces consequences beyond a controlled shutdown. The framework accepts the output of functional safety regulation. Where the SIS does not meet IEC 61511 requirements, the consequence ceiling does not hold. That is a process safety deficit that predates and outranks any security engagement. It is not a gap this framework fills. It is a condition that must be resolved before the framework's tier sequence produces its intended risk reduction.
* **Tier 2: IT/OT Boundary.** The primary barrier against the realized threat population, governing all connectivity crossing between IT and OT regardless of underlying network topology. The definitive test is **Island Mode** capability: the ability to sustain safe production for a prolonged period with all IT/OT connectivity severed, accepting the temporary loss of business integration and administrative functions.
* **Tier 3: DCS and Process Control.** The systems enabling direct process manipulation capability. Each distinct DCS, PLC network, or process control system is its own zone.
* **Tier 4: Process Operational Visibility.** Infrastructure providing operators with real-time process awareness: SCADA systems, historians, alarm management platforms. Each distinct system is its own zone.
* **Tier 5: Operational Support Infrastructure.** Foundational shared services including OT networks, shared storage, PKI, backup infrastructure, and time synchronization. Segmented where the architecture supports it.
* **Tier 6: Operational Health Monitoring.** A cross-stack program, not a zone. Deploys and activates threshold-based telemetry for all decay indicators enumerated during Tiers 1 through 5. Complete when every enumerated indicator is under active threshold alerting with a named response owner, and the monitoring infrastructure itself is subject to operational health oversight.
* **Tier 7: General Security Hygiene.** The boundary where consequence-driven investment ends and externally mandated hygiene begins. Scope is set by corporate IT framework mandates or regulatory requirements rather than by the site-specific risk model. Activities include patch cycles, vulnerability scanning, encryption at rest, adversarial detection, and SOC integration. Most sites reach Tier 7 with remaining budget exhausted. This is the expected and correct economic outcome of a rational sequenced investment model.

## 7. Zone Protection Sequence (Axis B(i))

Applies to Tiers 1 through 5. Every zone within these tiers is matured through this fixed sequence. Interior hardening is never the starting point for new investment. Pre-existing interior controls that predate the sequence are not forcibly removed. A working control does useful work regardless of whether it was deployed in the sequence this framework prescribes. The within-tier sequence governs the priority for new investment, not the disposition of existing controls. Pre-existing controls are re-evaluated during the attack surface assessment step. Where the maintenance cost of an existing control exceeds its protection value against the threat population that actually reaches the zone after isolation and recovery are verified, that cost is better redirected to completing foundational elements.

1. **Isolation verification:** The zone's assets are demonstrably separated from adjacent zones and external access paths. The architectural objective is to limit cross-zone dependencies and explicitly document what functionality is sacrificed during an isolation event. It is expected and acceptable for centralized logging, health metrics, and patch updates to break under isolation. The requirement is that the zone can safely sustain core production for a prolonged period.

2. **Recovery capability:** Logic and configurations are backed up to offline, attack-resistant storage on physically separate media. Integrity is verified through test restoration, not by confirming that backup files exist.

3. **Attack surface assessment:** Because step 1 is complete, all remaining paths crossing the isolated boundary are defined. Scope is determined by technical capability to affect the assessed zone, not by data flow direction or policy configuration. A connection is in scope if it carries or can trigger modification capacity within the zone through any chain of automated action. Human-mediated action is the scope boundary on the outbound side: a connection carrying data that a human reads and then acts upon is outside the assessed zone's attack surface, as the write action belongs to the zone the human operates from. Each in-scope path is documented with business justification, permitted protocols, and authentication requirements. Paths without current business justification are removed, not documented.

4. **Interior hardening:** Applied only where steps 1 through 3 leave a specific, credible residual risk. Interior hardening is the exception, not the default.

5. **Residual risk acceptance:** Formally signed by a named risk acceptor who understands what they are accepting. The residual risk register distinguishes three control states: **Technically Blocked** (prevented by enforced system configuration independent of human behavior; cannot be bypassed without modifying the configuration), **Technically Restricted** (limited by configuration but dependent on controlled processes; access is possible under defined conditions requiring deliberate action), and **Procedurally Controlled** (dependent on policy or human compliance with no technical enforcement). Every Procedurally Controlled item is a residual by definition, requires a named acceptor, and must be explicitly acknowledged as dependent on continued human compliance under operational pressure.

6. **Health baseline enumeration:** Identify the failure modes that would undermine the zone's isolation or recovery capability to the **Explicit Indicator Specification** standard. Pointing to a category is invalid. The standard requires four fields per indicator: the specific identity of the indicator, its current value, the defined threshold that triggers revalidation, and the named response owner.

   *Example:* "OT PKI root certificate, Site A engineering zone" is not a valid indicator specification. The valid specification is: Indicator: OT PKI root certificate, CN=SiteA-OT-RootCA. Current value: expires 2026-11-14. Threshold: 90 days prior to expiry. Response owner: OT Systems Engineer, [name].

   Monitoring activation for enumerated indicators is a Tier 6 activity, not a prerequisite for Tiers 1 through 5 completion. The obligation at this step is identification, ownership, and a defined verification schedule.

## 8. Program Governance (Axis B(ii))

Applies to Tiers 6 and 7. These tiers have no zone boundary, no attack surface to scope, and no isolation to verify. Completion logic differs accordingly.

**Tier 6** is complete when every indicator enumerated to Explicit Indicator Specification standard during Tiers 1 through 5 is covered by active threshold alerting with a named response owner, and the monitoring infrastructure itself is under operational health oversight. The coverage obligation is total: an indicator not under active alerting must be explicitly retained under a documented manual verification schedule with named ownership and justification for non-conversion. Partial coverage is Incomplete.

**Tier 7** has no equivalent completion sequence. Scope is defined by external mandate: corporate IT framework requirements, regulatory obligations, or both. The correct governance posture is a prioritized backlog with named owners, realistic timelines, and a documented rationale for sequencing decisions within the backlog. Activities within Tier 7 are legitimate and are also the lowest-ROI activities in the framework relative to the realized threat population. Their absence allows security posture to degrade slowly. Their presence does not compensate for incomplete structural foundations in Tiers 1 through 5.

## 9. Architectural Realities

### Centralized Management Platforms and Weaponization

IT identity management platforms, remote monitoring tools, and endpoint management agents are documented attack vectors where the platform's authorized reach and execution capability become the weapon. A shared management platform with an IT-connected control plane is a sanctioned channel that bypasses the hard IT/OT border by design. The resilience impact is identical whether the disrupting input is a malicious payload or a faulty update. OT endpoints must be managed by OT-dedicated management infrastructure. No single change or platform can be permitted to simultaneously disable multiple tiers or sites.

### Cloud Telemetry and Outbound Metrics

The belief that OT environments cannot send operational metrics to cloud platforms conflates the risk of centralized control with the risk of exported visibility. These are different risks. Outbound cloud telemetry is a permitted monitoring strategy under strict architectural constraints. The connection must be OT-initiated and strictly outbound. The platform must have zero control path capability: read-only by design, not by policy. It must be assessed, documented, and approved as a named Tier 2 boundary crossing. A telemetry platform with a control capability that is policy-disabled remains within scope until technical enforcement of the disablement is verified and documented.

### The Patching and Vulnerability Reality

CVE exploitation requires network reachability. A genuinely isolated OT asset with no reachable attack surface has near-zero security exposure from unpatched vulnerabilities. Patching is not a scheduled operational task in OT. It is a risk-based activity executed only where the tier risk assessment identifies a specific, reachable vulnerability requiring mitigation. Applying IT patch cadence to isolated OT assets is a framework import error that consumes operational resources without improving security posture.

### Legacy Systems

OT environments contain systems with operational lifespans of 15 to 30 years. This is the designed lifecycle of industrial control equipment, not a security deficiency. A legacy PLC or HMI operating behind a properly implemented Tier 2 boundary with no externally reachable attack surface is a managed asset, not a security liability requiring emergency replacement. Replacement is driven by operational supportability and spare parts availability. Security informs but does not drive this decision for assets behind effective boundary controls.

## 10. Governance, Defensibility, and the Professional Services Requirement

### Binary Completion

Binary completion replaces percentage maturity scores as the governance instrument. Tiers are Complete or Incomplete. There is no intermediate state.

Binary completion forces one of three explicit management decisions when a tier cannot be completed: allocate resources, formally accept residual risk with a named owner, or escalate. Constraints that cannot be resolved within the current planning cycle are documented as named blockers with dated remediation plans. The only outcome not permitted is not knowing where structural exposure exists.

Zone-level completion status is visible within each tier's governance record. A site with 14 of 15 zones complete at a given tier is Incomplete for that tier, but the governance record shows exactly where the gap is, what blocks it, and who owns the blocker. This is not a dashboard percentage. It is a named list of incomplete zones with documented blockers and named owners. Progress is visible. The tier does not turn green until the structural obligation is met.

### NIS2 Defensibility

The tier sequence produces the governance documentation that NIS2 Article 21 requires: structured risk identification, logical control selection sequenced by architectural dependency, and explicit risk acceptance with named owners. A decision to address Tier 2 before Tier 7 is not a decision to ignore regulation. It is a documented, risk-based roadmap that directly satisfies the proportionality mandate.

NIS2 incident reporting obligations also serve the framework's evidence base. As mandatory disclosure requirements produce a more comprehensive incident record at standard operators, the threat model review obligation operates against better data. The regulatory requirement for disclosure improves the evidence that grounds proportionate investment.

### Professional Services Requirement

The framework's logic is transferable. The specific instantiation is not. Tier structure validation, zone boundary determination, and threat scenario selection require simultaneous competence in process operations, functional safety, IT infrastructure, and OT security architecture. A framework document specifies the logic. Correct instantiation at a specific site requires practitioner judgment that the document cannot substitute for.

This is not a limitation specific to this framework. It is a structural property of any framework applied to heterogeneous industrial environments where no two sites share an architecture, a history, or a starting point. A framework that claims self-service applicability in those environments is making a promise the heterogeneity does not permit.

The entry cost difference between a control catalog and this framework is real. So is the output difference. A control catalog offers low entry cost, immediate artifact production, and self-service application. It does not require site-specific judgment. It also does not produce site-specific resilience. This framework requires expert engagement, produces slower output, and is designed to produce a posture rather than an artifact. The judgment the framework requires is not overhead added to a working process. It is the work that the control catalog skips.

Organizations that apply the framework without the practitioner judgment it requires will produce artifacts without producing posture. That is the same failure mode the framework diagnoses in coverage-based programs. It is worth stating directly.

## 11. Framework Maturity and Applicability

The tier structure presented here is a working model, not a validated standard. It has not been tested at scale across a broad range of industrial environments. Implementation will surface edge cases: zone boundary ambiguities, architectural configurations that do not map cleanly to the tier definitions, and completion criteria that prove unworkable in specific operational contexts. Where implementation reveals structural gaps, the tier model should be revised.

The specific tier sequence defined here is derived from the consequence profile of high-hazard continuous process environments operating under functional safety regulation (IEC 61511 and equivalent): facilities where the safety-instrumented system is the consequence ceiling and IT-origin boundary crossing is the dominant realized threat vector. This includes SEVESO-classified chemical facilities, refineries, and other process industry operations where IEC 61511 governs the safety lifecycle. The consequence profile, not the regulatory classification, drives the tier ordering.

Different operational contexts with different consequence profiles, different safety architectures, and different realized threat populations require a different tier derivation. Discrete manufacturing, pharmaceutical OT, and utilities carry different consequence ceilings and different boundary architectures. Applying this framework's tier sequence to those contexts without re-deriving from their specific consequence profile is a category error. The framework's logic (sequencing by consequence and dependency, barrier dimensioning, explicit stopping point) transfers. The specific tier order does not.

---

*© Mattias Pilroth. Published under CC BY 4.0. mattiaspilroth.com*