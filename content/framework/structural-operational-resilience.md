---
title: "The SOR Framework: Implementing Structural Operational Resilience"
date: 2026-03-22
lastmod: 2026-03-22
description: "A consequence-driven engineering framework for OT security in industrial environments. Addresses the realized threat population through sequenced tier-based controls, binary completion governance, and explicit residual risk ownership."
image: "images/og-sor-framework.jpg"
---

**An engineering discipline for OT security in high-consequence industrial environments.**

## 1. The Core Thesis: Miscalibration and Realized Threats

The operational technology security industry is miscalibrated. Vendor-driven threat models dominate the discourse and produce systematic resource misallocation at standard industrial operators.

The dominant realized threats are IT-origin lateral movement, ransomware spillover, and operational decay. Virtually all documented OT impact at standard operators traces to IT targeting that crossed into OT through inadequate boundary controls, or IT compromise that triggered precautionary OT shutdown. Catastrophic process events at regulated industrial facilities are not concealable. If OT-specific nation-state attacks against standard operators were producing consequences at scale, the incident record would show it.

Furthermore, modern OT environments running commodity hardware have accumulated IT-style failure modes. Software-defined dependencies do not age predictably. They expire, overflow, fragment, and fail invisibly until a process-critical moment. At current threat prevalence, this **Operational Decay** (silent degradation through certificate expiry, storage exhaustion, and database capacity overrun) is a highly probable source of OT disruption.

Process safety engineering offers the correct organizing principle for addressing these realities. A safety-instrumented system is not designed to eliminate every conceivable hazard. It is designed to interrupt credible paths to intolerable consequences, at barriers proportionate to the consequence severity, with explicit acceptance of residual risk by a named owner. The engineer does not install five independent shutoff valves on a chlorine line because four might fail. The credible failure modes are identified, barriers are placed at the points where they interrupt realistic paths to harm, and the program stops where the cost of additional protection exceeds the risk reduction it delivers. OT security should follow exactly the same engineering logic. The question is not how many controls can be implemented. It is which controls interrupt credible paths to physical consequence, at what cost, and where the rational stopping point is.

The correct instrument to address these realities is a tier-based, sequenced investment model operationalized through the Structural Operational Resilience (SOR) Framework.

## 2. Foundational OT Prerequisites

Before any tier is assessed, two structural conditions must be verified as non-negotiable prerequisites.

1. **No OT endpoint has internet access.** OT assets do not browse the web, receive email, run office productivity software, or connect to any internet-facing service directly. Tasks requiring internet access are performed on IT-protected assets, and results are transferred into OT through controlled boundary crossings.
2. **IT protects OT, not equivalent to IT.** The IT security layer is the primary barrier against the realized threat population. This protection relationship functions only if OT is genuinely isolated from the internet.

A site unable to demonstrate both conditions is categorized as **Unclassified (Architecturally Invalid)**. This is a transparent management signal requiring immediate capital and engineering intervention. An OT environment with internet-connected endpoints is not an OT environment with security gaps. It is an IT environment with industrial software installed.

Only once these prerequisites are met does a site enter the framework at Tier 0, beginning work toward Tier 1 completion.

## 3. The 7-Tier Progression Model (Axis A)

Priority order reflects consequence severity and architectural dependency. A higher tier cannot be reported Complete until all lower tiers are verified Complete.

* **Tier 1: Safety Instrumented Systems (SIS).** The consequence ceiling for the facility. If the SIS functions as designed, no cyber attack on any other system produces consequences beyond a controlled shutdown.
* **Tier 2: IT/OT Boundary.** The primary barrier against the realized threat population, governing all connectivity crossing between IT and OT regardless of underlying network topology. The definitive test is **Island Mode** capability: the ability to sustain safe production for a prolonged period with all IT/OT connectivity severed, accepting the temporary loss of business integration and administrative functions.
* **Tier 3: DCS and Process Control.** The systems enabling direct process manipulation capability.
* **Tier 4: Process Operational Visibility.** Infrastructure providing operators with real-time process awareness including SCADA, historians, and alarm systems.
* **Tier 5: Operational Support Infrastructure.** Foundational shared services including OT networks, shared storage, PKI, backup infrastructure, and time synchronization.
* **Tier 6: Operational Health Monitoring.** The deployment and activation of active threshold telemetry for all decay indicators enumerated in Tiers 1 through 5.
* **Tier 7: Operational Security Maintenance.** Patch cycles, vulnerability tracking, deep OT visibility, adversarial detection, and SOC integration. Most sites will stall at Tier 7 due to rational funding ceilings. This is the expected and correct economic outcome.

## 4. The 6-Step Within-Tier Sequence (Axis B)

Every tier is matured through a fixed sequence. Interior hardening is never the starting point.

1. **Isolation verification:** The tier's assets are demonstrably separated from adjacent tiers and external access paths. The architectural objective is limiting cross-zone dependencies and explicitly documenting what functionality is sacrificed during an isolation event. It is expected and acceptable for centralized logging, health metrics, and patch updates to break under isolation. The requirement is that the zone can safely sustain core production for a prolonged period.

2. **Recovery capability:** Logic and configurations are backed up to offline, attack-resistant storage on physically separate media. Integrity is verified through test restoration, not by confirming that backup files exist.

3. **Attack surface assessment:** Because step 1 is complete, all remaining paths, interfaces, and dependencies crossing the isolated boundary are now defined and documentable. Scope is determined by technical capability to affect the assessed zone, not by data flow direction or policy configuration. Each in-scope path is documented with business justification, permitted protocols, and authentication requirements. Paths without current business justification are removed, not documented.

4. **Interior hardening:** Applied only where steps 1 through 3 leave a specific, credible residual risk. Interior hardening is the exception, not the default.

5. **Residual risk acceptance:** Formally signed by a named risk acceptor who understands what they are accepting. The residual risk register distinguishes three control states: **Technically Blocked** (prevented by enforced system configuration independent of human behavior; cannot be bypassed without modifying the configuration); **Technically Restricted** (limited by configuration but dependent on controlled processes; access is possible under defined conditions requiring deliberate action); and **Procedurally Controlled** (dependent on policy or human compliance with no technical enforcement). Every Procedurally Controlled item is a residual by definition, requires a named acceptor, and must be explicitly acknowledged as dependent on continued human compliance under operational pressure.

6. **Split Execution (Health Enumeration or Monitoring Activation):**
   * **For Tiers 1 through 5 (Enumeration):** Identify the failure modes that would undermine the tier's isolation or recovery capability to the **Explicit Indicator Specification** standard. Pointing to a category is invalid. The standard requires four fields per indicator: the specific identity of the indicator, its current value, the defined threshold that triggers revalidation, and the named response owner.

     *Example:* "OT PKI root certificate, Site A engineering zone" is not a valid indicator specification. The valid specification is: Indicator: OT PKI root certificate, CN=SiteA-OT-RootCA. Current value: expires 2026-11-14. Threshold: 90 days prior to expiry. Response owner: OT Systems Engineer, [name].

   * **For Tier 6 (Monitoring Activation):** Deploy active threshold telemetry for all indicators enumerated at Tiers 1 through 5. Manual tracking of enumerated indicators is a Tier 1 through 5 activity. Tier 6 replaces manual tracking with automated alerting at defined thresholds.

## 5. Architectural Realities vs. IT Assumptions

### Centralized Management Platforms and Weaponization

IT identity management platforms, remote monitoring tools, and endpoint management agents are frequently compromised and weaponized. The attacker uses the platform's authorized reach and execution capability without a separate payload. A shared management platform with an IT-connected control plane is a sanctioned channel that bypasses the hard IT/OT border by design. The resilience impact is identical whether the disrupting input is a malicious payload or a faulty update. OT endpoints must be managed by OT-dedicated management infrastructure. No single change or platform can be permitted to simultaneously disable multiple tiers or sites.

### Cloud Telemetry and Outbound Metrics

The belief that OT environments cannot send operational metrics to cloud platforms conflates the risk of centralized control with the risk of exported visibility. These are different risks. Outbound cloud telemetry is a permitted monitoring strategy under strict architectural constraints. The connection must be OT-initiated and strictly outbound. The platform must have zero control path capability, meaning read-only by design. It must be assessed, documented, and approved as a named Tier 2 boundary crossing. The zone boundary scoping rule applies: assessment scope is determined by technical capability, not policy configuration.

### The Patching and Vulnerability Reality

In IT, unpatched vulnerabilities are an emergency. In OT, CVE exploitation requires network reachability. A genuinely isolated OT asset with no reachable attack surface has near-zero security exposure from unpatched vulnerabilities. Patching is not a scheduled operational task in OT. It is a risk-based activity executed only where the tier risk assessment identifies a specific, reachable vulnerability requiring mitigation. Applying IT patch schedules to OT is a framework import error that consumes operational resources without improving security posture for isolated assets.

### Legacy Systems

OT environments contain systems with operational lifespans of 15 to 30 years. This is the designed lifecycle of industrial control equipment, not a security deficiency. A legacy PLC or HMI operating behind a properly implemented Tier 2 boundary with no externally reachable attack surface is a managed asset, not a security liability requiring emergency replacement. Replacement is driven by operational supportability and spare parts availability. Security informs but does not drive this decision for assets behind effective boundary controls.

## 6. Governance and Defensibility

Binary completion replaces percentage maturity scores as the governance instrument. Tiers are Complete or Incomplete. There is no intermediate state.

Binary completion forces one of three explicit management decisions when a tier cannot be completed: allocate resources, formally accept residual risk with a named owner, or escalate. Constraints that cannot be resolved within the current planning cycle are documented as named blockers with dated remediation plans. The only outcome not permitted is not knowing where structural exposure exists.

Organizations that build toward this standard will find that regulatory defensibility under mandates like NIS2 Article 21 is a natural consequence of the program. Structured risk identification, logical control selection sequenced by architectural dependency, and explicit risk acceptance satisfy the core requirement for appropriate and proportionate security measures. A decision to address Tier 2 before Tier 7 is not a decision to ignore regulation. It is a documented, risk-based roadmap that directly satisfies the proportionality mandate.

---

*© Mattias Pilroth. Published under CC BY 4.0. mattiaspilroth.com*