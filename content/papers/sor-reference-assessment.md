---
title: "SOR Framework: Practitioner Reference and Illustrative Assessment"
date: 2026-05-14
lastmod: 2026-05-14
description: "A compressed reference map of the SOR Framework and an illustrative Stage 1 and Stage 2 assessment for a composite high-hazard continuous process site."
image: "images/og-sor-companion.jpg"
---

This document shows what the SOR Framework produces when applied to a composite illustrative environment, and should be read alongside <a href="/papers/sequenced-ot-resilience/" class="article-link-text" data-umami-event="click-assess-sor">Sequenced OT Resilience Framework</a>, which defines the model this document executes.

---

## Framework overview

**Four core constructs**

- **Consequence ceiling** — The verified architectural condition where unacceptable consequence cannot be reached through a single compromise.
- **Governed exposure** — Every contact point assessed, documented, and owned. Three states: acceptable governed, exception-governed, ungoverned. Completion = zero ungoverned exposure within assessed scope.
- **Contact boundary** — The governed perimeter between zones and external dependencies.
- **Health baseline** — Indicators that confirm the system remains in its assessed state. Each specified to four fields: identity, current value, threshold, owner.

**Three operating rules**

1. Dependency-based sequencing: Zones are addressed in consequence order. Structural conditions are established before boundary assessment. Controls are derived last from remaining exposure.
2. Contact boundary assessment: Every crossing is evaluated for mechanism appropriateness before control application. Architectural redesign is the primary exposure reduction instrument.
3. Constraint verification: Binary and observed at the operational system, not asserted in documentation.

**Six stages**

1. Establish and verify the consequence ceiling.
2. Govern the IT/OT boundary as the primary adversarial barrier.
3. Govern control zones in consequence order.
4. Govern visibility infrastructure in consequence order.
5. Govern shared operational support services.
6. Govern the monitoring infrastructure that delivers automated visibility for the health baseline indicators that warrant it.

**Completion**

A stage is Governed or Incomplete. Incomplete stages carry explicitly named unassessed scope. When all stages within assessed scope reach Governed, the organisation holds a governed exposure position across the full consequence order. Completion is defined within assessed scope and under explicit architectural assumptions.

**Controls**

Every control exists because a specific pathway requires it. Every absent control is absent because no assessed pathway required it, and that determination is a documented finding, not an unmarked gap.

**Failure modes**

Named in Section 11.2 of the main specification. They define the conditions under which the framework produces artifacts without producing posture. Reading them before beginning the stage sequence is recommended.

---

## Illustrative assessment: Stage 1 and Stage 2

**Site context:** Illustrative composite site representing a high-hazard continuous process environment. The unacceptable consequence is loss of containment from uncontrolled reaction pressure. The safety case identifies independent SIS trips and mechanical relief as protection layers. The DCS controls normal operation. The SIS is intended to remain functionally independent from the DCS.

**Site components and their relationships:**

- DCS (multiple loops, common engineering domain)
- SIS (independent logic solver, engineered via SIS engineering workstation)
- Historian (receives data from DCS and SIS, pushes to IT-side staging server)
- OT domain controllers (joined to OT Active Directory, serving the OT environment)
- Engineering workstations for DCS and SIS (separate hardware)
- IT/OT firewall pair
- OT DMZ (jump host, vendor VPN landing, historian replication target)
- Vendor remote access (VPN to OT DMZ jump host)
- Enterprise EDR (deployed across OT endpoints, managed by IT)
- Enterprise backup platform (IT-managed)
- Business reporting (connected to OT historian)

---

### Stage 1: Consequence structure

**Assessment scope:** Verify that the claimed consequence ceiling holds in cyber-relevant operating state. Evidence base: safety case and cause and effect matrix, SIS and DCS architecture drawings, engineering workstation topology, credential architecture across DCS and SIS engineering systems, historian and alarm integration paths, remote vendor access procedures, walkdown of SIS cabinets and IT/OT boundary devices. All constraint claims verified directly at operational systems against current configuration.

---

**S1-F1: Shared OT domain credentials remove cyber independence between DCS and SIS engineering**

**Finding:** DCS and SIS engineering functions operate on separate physical workstations, both joined to the same OT Active Directory domain. Domain administrator credentials are common across both environments. Any user with domain administrator rights can authenticate to either engineering workstation and access both configuration environments from the same credential set. Physical hardware separation does not constitute architectural independence at the credential layer.

**Operational consequence:** Compromise of OT domain credentials, or of any system holding domain administrator access, provides a single authenticated path into both the DCS and SIS modification environments simultaneously. The claimed independence between DCS and SIS engineering does not hold.

**Governance state:** Requires remediation. Stage 1 cannot reach Governed until separate credential domains are established for DCS and SIS engineering with no shared administrative path, and verified at the operational systems.

---

**S1-F2: DCS override interface can hold SIS trip functions in a non-actuating state**

**Finding:** The DCS has an interface to the SIS that can be used to place trip functions in a non-actuating state. The interface does not enforce constraints sufficient to prevent a compromised DCS from defeating the trip function independently of the SIS.

**Operational consequence:** A compromised DCS with access to the override interface can hold one or more SIS trip functions in a non-actuating state without requiring compromise of the SIS itself. A single control system compromise enables a path to loss of containment.

**Governance state:** Ceiling invalidation finding. Requires remediation. Stage 1 cannot reach Governed until the interface constraints are revised and verified at the system such that no reachable condition allows a single DCS compromise to produce a non-actuating trip function state. While remediation is outstanding, formal exception-governed acceptance is required from the SIS responsible engineer, safety manager, and operations manager, with a documented remediation timeline and stated compensating measures.

---

**S1-F3: SIS status data received by historian through constrained read-only path**

**Finding:** The SIS sends selected status and trip state data to the historian through a constrained interface. No write path from historian to SIS was identified. No shared credential was identified.

**Operational consequence:** Historian compromise may degrade control room visibility of SIS state. No modification capability into SIS logic or trip function exists through this path.

**Governance state:** Acceptable governed.

---

**Stage 1 status: Incomplete. Stage 2 closeable: No.**

The consequence ceiling claimed by the safety case does not hold in the current operating state. Shared OT domain credentials remove independence between DCS and SIS engineering at the credential layer (S1-F1). The DCS override interface permits trip functions to be held in a non-actuating state through a single control system compromise (S1-F2). Both conditions must be resolved and verified before the ceiling is verifiable.

**Completion condition:** Separate SIS and DCS engineering credential domains with no shared administrative path, verified at the operational systems. Override logic revised so maintenance bypass degrades availability margin without disabling the trip function, verified at the operational system.

Stage 2 assessment proceeds while Stage 1 remains open. Findings can be individually assessed, mitigated, and exception-governed, and those governance states hold within Stage 2 scope. Stage 2 completion cannot be assigned until Stage 1 is closed: a boundary that governs every contact point still does not govern a consequence ceiling that does not hold. Every Stage 2 residual accepted during this period is accepted against an open consequence ceiling. A finding that would be exception-governed at acceptable risk under a verified ceiling requires materially higher escalation and stronger compensating measures while Stage 1 remains unresolved. Named owners of Stage 2 exception-governed findings carry that conditional acceptance until Stage 1 is closed.

---

Stage 1 determines whether the environment is consequence-bounded at all. Stage 2 assumes that condition and evaluates whether the IT/OT boundary enforces it or bypasses it.

---

### Stage 2: The IT/OT boundary

**Assessment scope:** Determine whether the IT/OT boundary performs a genuine boundary function and whether every contact point is governed at the lowest-exposure mechanism consistent with operational need. IT security maturity assessed as input: MFA deployed for remote access but not enforced for all privileged IT accounts; EDR widely deployed and centrally managed from IT infrastructure; vendor remote access managed outside a consistent IT governance process. The required boundary posture is treated as elevated accordingly.

The Stage 2 findings are presented in four groups: findings requiring remediation, a finding requiring verification before a governance state can be assigned, a finding producing pathway-derived elimination, and findings producing acceptable governed status. The grouping reflects the type of output the assessment produces at each contact point, not a sequence of assessment steps. The full exception-governed acceptance record format is illustrated at S2-F4. The same format applies to all exception-governed acceptances in this and subsequent stages.

---

#### Findings requiring remediation

These contact points cannot yet be assigned a stable governance state. The contact point population is undefined, the current mechanism introduces exposure that has not been consciously accepted, or architectural change is required before a governed position is achievable.

---

**S2-F1: Firewall permits broad IT subnet access to OT historian and engineering subnet**

**Finding:** Firewall rules allow broad IT subnet access to the OT historian and selected engineering workstation addresses. Rules are not tied to named operational capabilities or defined delivery mechanisms. Access is scoped to address ranges rather than to service flows.

**Operational consequence:** Compromise of IT infrastructure within the permitted subnet range can reach OT assets beyond any specific business function the rules were intended to enable. The boundary does not constrain contact to defined mechanisms with defined exposure profiles.

**Governance state:** Ungoverned. A governance state cannot be assigned until the contact point population is defined and mechanisms are specified. Required action: replace subnet-level rules with named service flows tied to specific operational capabilities; remove direct IT access to the engineering subnet.

---

**S2-F2: Business data extraction is IT-initiated into OT**

**Finding:** Enterprise reporting systems initiate live queries into the OT historian. IT-side systems control when OT-side historian operations occur and can vary those operations at will. The historian has no mechanism to constrain query frequency or scope from the IT side.

**Operational consequence:** A compromised IT-side reporting system can drive repeated or varied OT-side historian interactions. IT-side initiation of OT operations is inconsistent with a genuine boundary function.

**Mechanism assessment:** OT-initiated extraction to a DMZ staging area, consumed by IT-side reporting systems from the DMZ copy, delivers equivalent business reporting capability without IT-side systems initiating OT-side operations.

**Governance state:** The mechanism assessment identifies OT-initiated extraction to a DMZ staging area as the lower-exposure alternative. Where the operator accepts IT-initiated live queries into the OT historian as the justified mechanism, the governance state is acceptable governed: named acceptance from the business reporting owner and OT operations manager with documented consequence statement covering what a compromised IT-side reporting system could produce, and defined review conditions. Where the operator intends to move to the OT-initiated mechanism, the governance state is exception-governed during the redesign period, with confirmed migration plan required.

---

**S2-F3: Vendor VPN provides standing access to OT jump host**

**Finding:** Vendor VPN accounts remain enabled outside maintenance windows. Access lands on a jump host with routing capability into multiple OT zones. Access is scoped to the vendor's operating model, not to minimum necessary privilege for defined tasks. Session witnessing is procedural rather than enforced by the access mechanism. Shared vendor credentials identified; individual session accountability is not available.

**Operational consequence:** Compromise of vendor credentials, or of a vendor-side system with VPN access configured, provides a persistent direct path into OT engineering environments between maintenance events.

**Mechanism assessment:** Time-bounded task-scoped access with individual named accounts and enforced session recording delivers equivalent vendor diagnostic capability with standing exposure reduced to near zero between maintenance events.

**Governance state:** The mechanism assessment identifies time-bounded task-scoped access with individual named accounts and enforced session recording as the lower-exposure alternative. Where the operator accepts vendor-scoped standing access as the justified mechanism for their operational model, the governance state is acceptable governed: named acceptance from the OT operations manager with documented consequence statement covering what credential compromise or vendor-side system compromise produces at each reachable zone, and defined review conditions. Where the operator intends to move to the constrained mechanism, the governance state is exception-governed during the transition period, with confirmed implementation plan required.

---

**S2-F4: Enterprise EDR management carries modification capability across OT endpoints**

**Finding:** The EDR platform is managed from IT infrastructure and carries remote command capability into OT endpoints, including process isolation, process termination, and software deployment. The management plane is reachable from IT and operates under IT-side identity and access controls.

**Operational consequence:** Compromise of the EDR management plane, or a misapplied management action, can disrupt OT hosts through a tool deployed for protection. The consequence of a management plane action is not uniform across zones: process isolation or termination on a Stage 1 or Stage 3 asset carries a materially different operational outcome than the same action on a visibility or support infrastructure host.

**Mechanism assessment:** Lower-exposure options exist: OT-local management plane separated from IT, policy-only relay without remote command capability, or reduced action sets for high-consequence assets that exclude process termination and software deployment. The appropriate mechanism is consequence-scaled by zone.

**Governance state:** The mechanism assessment identifies consequence-scaled alternatives. The governance position depends on the operator's assessment of what the management plane capability is justified at each zone.

Where the operator accepts the current IT-managed mechanism for lower-consequence zones where management plane compromise is within operational tolerance, the governance state for those zones is acceptable governed: named acceptance from the OT operations manager with documented consequence statement per zone and defined review conditions.

Where the operator accepts the current mechanism for Stage 1 and Stage 3 zones, the consequence of management plane compromise at those zones must be assessed against the open consequence ceiling established in Stage 1. Acceptance at those zones requires materially stronger justification, named ownership from operations management, and compensating measures that reduce the action set available to the management plane.

Where the operator intends to move to a lower-exposure mechanism, the governance state is exception-governed during the transition period. The acceptance record below documents that position for the full estate pending mechanism review.

**Exception-governed acceptance record: S2-F4**

**Operational consequence accepted:** The EDR management plane is reachable from IT infrastructure and carries remote command capability into OT endpoints. A compromise of the IT-side management plane provides a credentialed path to execute process isolation, process termination, or software deployment against any OT host enrolled in the platform. The credible operational outcome from a single management plane action is loss of control or unplanned shutdown of the affected production train. Estimated production impact: EUR 350-500k per day until the affected hosts are restored and verified. Worst credible outcome: simultaneous disruption across multiple production trains if the management plane action is policy-wide rather than host-specific, enabled by the fact that the management plane credential path is not scoped per zone. This acceptance is made against an open consequence ceiling: Stage 1 findings S1-F1 and S1-F2 remain unresolved, and the worst credible outcome is not yet architecturally bounded.

**Remediation expectation:** OT-local EDR management plane separated from IT identity infrastructure, with reduced action sets for high-consequence assets (process isolation permitted; process termination and software deployment from the management plane prohibited). Implementation target: 6 months from the date of this acceptance.

**Compensating measures during interim:**
- Reduced EDR action set deployed for Stage 1 zones: alerting only, no remote execution capability.
- EDR management plane access subject to enhanced monitoring and named-account requirement; shared service accounts revoked.
- OT incident response runbook explicitly addresses scenarios initiated from the EDR management plane, including management plane isolation procedure.

**Review conditions (triggers immediate revalidation):**
- Annual revalidation.
- IT identity infrastructure scope expands to cover additional OT assets.
- EDR vendor consolidates or modifies the management plane in ways that increase the IT-side action set.
- Credible threat intelligence indicates active exploitation of EDR management infrastructure against industrial targets.
- Stage 1 findings S1-F1 or S1-F2 are remediated: the consequence weight of this acceptance changes when the ceiling is verified.

---

**S2-F5: IT-managed backup platform pushes into OT using high-privilege credentials**

**Finding:** The backup platform initiates connections from IT into OT hosts using high-privilege credentials. The credential set is persistently active and reachable from IT. Backup and restore operations share the same credential path: the standing credential used for scheduled backup is sufficient to execute modification and destruction operations across all enrolled OT hosts. Enrolled OT hosts include DCS servers, engineering workstations, historian, OT domain controllers, and visibility infrastructure. SIS engineering workstations are not enrolled in this platform.

**Operational consequence:** Compromise of the backup management plane produces simultaneous modification capability across live OT systems and the recovery artifacts those systems depend on, through a single credential path that is persistently active and reachable from IT.

**Mechanism assessment:** Pull-based backup, where OT-side agents initiate outbound connections to a controlled staging location, delivers equivalent recovery capability without maintaining a standing high-privilege inbound path from IT. OT restore is planned maintenance; the rapid-restore justification for standing high-privilege inbound access does not apply.

**Governance state:** The mechanism assessment identifies pull-based backup as the lower-exposure alternative. Where the operator accepts the current push-based mechanism, the governance state is acceptable governed: named acceptance from the OT operations manager with documented consequence statement covering the specific condition that backup credentials are sufficient to execute modification and destruction operations across all enrolled OT hosts simultaneously, and defined review conditions. The cross-zone reach of the shared credential path and the absence of separation between backup and destruction capability are the specific conditions the named owner must be able to relate to operational consequence. Where the operator intends to move to the pull-based architecture, the governance state is exception-governed during the transition period, with confirmed assessment timeline for the revised architecture required.

---

**S2-F6: IT/OT boundary administration uses enterprise identity**

**Finding:** Firewall pair and OT DMZ are administered through enterprise identity infrastructure. Firewall rule changes and DMZ configuration changes require no OT-specific approval workflow. Access to boundary device management interfaces is controlled by the same Active Directory domain used for general IT operations.

**Operational consequence:** Compromise of enterprise identity or IT administration infrastructure can alter IT/OT boundary policy, disable logging, enable contact points, or remove governing rules without OT-specific oversight. Boundary policy is controllable from the trust domain it is designed to constrain.

**Governance state:** The mechanism assessment identifies OT-owned boundary administration credentials with OT security owner authorisation for rule changes as the lower-exposure alternative. The current mechanism has a structural property that the lower-exposure alternative resolves: the boundary is administrable from the trust domain it is designed to constrain. Where the operator accepts the current mechanism, the governance state is acceptable governed: named acceptance from the OT operations manager with documented consequence statement covering the specific condition that enterprise identity compromise enables unrestricted boundary policy modification, and defined review conditions including offline configuration backup and verified known-good baseline as minimum compensating measures. The logical dependency between boundary integrity and enterprise identity security is the specific condition the named owner must be able to relate to operational consequence. Where the operator intends to establish independent boundary administration, the governance state is exception-governed during the transition period, with confirmed implementation timeline and OT security owner authorisation requirement for all boundary rule changes established as an interim compensating measure.

---

**S2-F7: Boundary configuration recovery ungoverned**

**Finding:** No verified procedure exists for restoring the IT/OT boundary configuration following firewall failure or replacement. Configuration backups exist but have not been tested against a restoration scenario. No named recovery owner is assigned. OT DMZ rebuild procedure depends on IT infrastructure teams outside the OT incident response process.

**Operational consequence:** Firewall or DMZ failure during or following an incident requires restoration from an unverified configuration. Recovery under incident conditions without a verified procedure and a named OT-capable recovery owner risks restoring the boundary incorrectly, incompletely, or not at all within an operationally acceptable timeframe.

**Governance state:** Ungoverned. Recovery capability is a stage completion criterion. Stage 2 cannot reach Governed until this finding is resolved. Required action: verify offline configuration backup against a defined restoration scenario; document boundary recovery procedure with named OT recovery owner capable of executing without IT team involvement; define compensating measures and authorisation path for boundary-down operation.

---

#### Finding requiring verification

This contact point cannot be assigned a governance state from documentation alone. A configuration verification is required at the operational system before the finding can be closed.

---

**S2-F8: Cloud monitoring gateway — write-back capability not verified**

**Finding:** A vendor cloud monitoring gateway in the process network maintains outbound connectivity to vendor cloud endpoints. Whether the connection permits vendor-side initiation of actions on OT assets has not been verified at the operational system. Vendor documentation states telemetry-only, but configuration verification is outstanding.

**Operational consequence:** Write-back or command capability on this connection would enable a path to OT modification through vendor cloud platform compromise or misuse, bypassing IT/OT boundary governance. A confirmed telemetry-only connection with no inbound path is assessable at a low exposure level.

**Governance state:** Cannot be assigned until write-back capability is verified at the operational system against current configuration, not from vendor documentation. Required action: validate actual capability of the vendor cloud platform over OT assets via this connection; establish whether any inbound path exists; assign governance state from verified configuration.

---

#### Finding producing pathway-derived elimination

The pathway assessment for this contact point establishes that the mechanism introduces more assessed exposure than the control it enables can eliminate. The justification for the control did not survive pathway analysis. The assessment output is a recommendation for elimination; the operator's acceptance of that recommendation is the governance decision.

---

**S2-F9: Hardware management interface — modification pathway exceeds assessed protection value**

**Finding:** An out-of-band hardware management interface (iDRAC-class) was deployed across OT servers to support a quarterly firmware patching schedule. The interface provides hardware-level access including power cycling, BIOS modification, and remote console over a persistent network path reachable from IT.

**Pathway assessment of the patching schedule:** Firmware patching is a coverage-model control. It reduces the vulnerability window on server hardware components across the enrolled population without reference to whether those vulnerabilities are reachable through an assessed pathway. In this architecture, the OT servers enrolled in the management platform are not reachable from adversarial entry points at the firmware attack surface. Firmware-layer exploitation requires a reachable network path to the management interface, not a reachable network path to the servers themselves. The servers' exposure profile, as defined by the Stage 2 boundary and zone architecture, does not include a route from adversarial actors to the hardware management layer. The patching schedule eliminates vulnerabilities in hardware components that are not reachable given that exposure profile. Its protection value cannot be assessed against a specific pathway, because no such pathway exists.

**Operational consequence:** The persistent management plane enables hardware-level modification capability across all enrolled OT hosts through a network path reachable from IT. This is a real, assessed modification pathway into the OT environment. The patching schedule that justified its deployment addresses a vulnerability class that is not reachable via the servers' exposure profile. The mechanism introduces more assessed exposure than the control it enables can eliminate, because the control's protective effect requires an adversarial route that does not exist in this architecture.

**Mechanism assessment:** No lower-exposure mechanism delivers hardware-level remote management. The floor for this capability is elimination. The firmware currency requirement that justified deployment is met through a controlled offline process during scheduled maintenance, without a persistent network-accessible management path.

**Governance state:** The pathway assessment establishes that the persistent management plane introduces a real modification pathway into the OT environment while the control it delivers addresses a vulnerability class with no assessed adversarial route in this architecture. The mechanism introduces more exposure than it eliminates.

Where the operator accepts the pathway assessment, the correct output is elimination: hardware management interfaces decommissioned, network paths closed, and firmware currency maintained through a controlled offline process during scheduled maintenance. Both the elimination of the management plane and the discontinuation of the automated patching schedule are documented findings, not unmarked gaps. Firmware currency remains a requirement; the mechanism for maintaining it changes.

Where the operator does not accept the pathway assessment and wishes to retain the management interface, the governance state is exception-governed: named acceptance from the OT operations manager with documented consequence statement covering the modification capability the management plane introduces, and confirmed justification for why the firmware patching value offsets that exposure at this site. The pathway analysis must be addressed in the justification, not assumed away.

---

#### Findings producing acceptable governed status

These contact points carry no assessed modification pathway at their current mechanism. A coverage framework would mandate controls at both. No assessed pathway at either contact point requires those controls.

---

**S2-F10: OT-to-IT process data feed — no modification pathway exists; endpoint hardening not required at this contact point**

**Finding:** The OT historian pushes selected process data to an IT-side staging server on a defined schedule. The connection is OT-initiated, outbound only, and constrained to a named data protocol on a defined port. No IT-side system has a connection path back to the historian. No shared credential exists between the historian and any IT system. No management-plane dependency was identified.

**Operational consequence:** Compromise of the IT-side staging server does not enable a modification path into the historian or the OT network through this contact point. The contact point carries process data outbound and nothing inbound.

**Governance state:** Acceptable governed. No assessed pathway reaches the historian through a vector that endpoint hardening would interrupt at this contact point. Endpoint hardening on the historian is not a required control derived from this pathway. A coverage framework would mandate it regardless. The control is absent because no pathway requires it, not because the assessment did not reach it. If a modification path is added to this contact point in future, the finding changes and this governance state reverts.

---

**S2-F11: Constrained vendor telemetry connection — acceptable governed**

**Finding:** A process equipment vendor receives operational telemetry from dedicated field instruments through an outbound-only encrypted connection to a vendor cloud endpoint. The connection is initiated by the field instrument; the instrument has no connection to the OT network or any OT host and communicates directly with the vendor cloud. No inbound path from the vendor cloud to any OT asset was identified.

**Governance state:** Acceptable governed.

---

### Stage 2: Controls derived from pathway assessment

The following controls exist because specific pathways require them. Each is absent from the Stage 2 output for zones or contact points where the relevant pathway does not exist. This is the structural difference from catalog coverage: a catalog deploys controls uniformly; the pathway assessment deploys them where the specific pathway exists and documents their absence where it does not.

---

**S2-C1: Boundary device firmware currency — derived from boundary function dependency**

**Pathway:** The IT/OT firewall pair performs the Stage 2 boundary function. The boundary function depends on the integrity of the firewall operating system and rule enforcement logic. Exploitable vulnerabilities in unpatched firewall firmware enable boundary bypass or rule manipulation that bypasses all other Stage 2 governance.

**Derived control:** Firewall firmware maintained within vendor-supported versions, with a defined patching cadence and a named owner responsible for firmware currency. This control is derived from the boundary dependency, not from a patch management catalog entry. A firewall that cannot be patched within the site's operational constraints requires a compensating mechanism or replacement; the control cannot be deferred without the boundary function being reported as not verifiable.

**Governance state:** Required. Boundary cannot be reported as Governed if the device performing the boundary function is running end-of-life firmware with known exploitable vulnerabilities.

---

**S2-C2: Certificate validity on authenticated boundary connections — derived from credential decay pathway**

**Pathway:** The vendor VPN gateway and EDR management plane both use certificate-based authentication. Certificate expiry on either connection degrades the authentication assurance of the access mechanism, providing a credential decay pathway that undermines the governed exposure position of every OT zone the connection reaches. Decay in this case is not hardware failure or storage exhaustion; it is a predictable scheduled event that produces a governance gap if not managed.

**Derived control:** Certificate renewal on a defined cadence before expiry, with a named owner responsible for each authenticated boundary connection. Renewal is a contact point maintenance requirement derived from the authentication dependency of the governed access mechanism. An expired certificate degrades the authentication assurance the contact point governance record depends on and requires revalidation of the contact point governance state.

**Governance state:** Required. Expiry date and renewal cadence are documented in the contact point governance record, not the zone health baseline. Threshold crossing triggers revalidation of the contact point governance state. Where Stage 6 evaluates automated monitoring, certificate expiry tracking on authenticated boundary connections is a candidate indicator.

---

**S2-C3: Enforced session recording on high-consequence vendor access paths — derived from consequence level of reachable zones**

**Pathway:** S2-F3 identifies that vendor VPN access reaches zones whose compromise contributes to the consequence ceiling assessment. Where vendor access is governed at a time-bounded task-scoped mechanism, a named vendor session has authenticated access to specific OT assets during the approved window. No mechanism other than session recording constrains what an authenticated session does within its authorised scope. The consequence level of the reachable zones determines whether the residual of authenticated but unwitnessed access is acceptable.

**Derived control:** Enforced session recording for vendor access to Stage 1 and Stage 3 zones. Recording is enforced by the access mechanism, not by procedural requirement. Recording is not required for vendor access to lower-consequence zones where the residual of unwitnessed access is assessed as acceptable given the consequence profile. The control is consequence-scaled, not uniformly applied.

**Governance state:** Required for high-consequence zone access. Acceptable governed without recording for lower-consequence access paths where the consequence assessment supports it.

---

**S2-C4: Immutable backup storage for high-consequence zone configurations — derived from destruction and recovery defeat pathway**

**Pathway:** S2-F5 identifies that the current backup mechanism provides a simultaneous attack surface against live OT systems and recovery artifacts through a shared credential path. Where backup is governed at a pull-based mechanism, the backup storage target is the remaining attack surface: a compromised backup storage system could corrupt or destroy recovery artifacts without touching live OT systems. For high-consequence zones, loss of recovery capability compounds the impact of any destructive event.

**Derived control:** Immutable backup storage for Stage 1 and Stage 3 zone configurations, where immutable means the backup data cannot be modified or deleted through the same credential path used to write it. Immutability is verified at the storage system, not asserted in policy. This control is derived from the pathway that links backup storage compromise to recovery capability defeat in the specific architecture at this site.

**Governance state:** Required for high-consequence zone backup targets. Derived from the pathway, not from a uniform backup hardening policy.

---

**S2-C5: OT-local NTP with no internet synchronisation path — derived from time integrity pathway**

**Pathway:** OT infrastructure synchronises time from an NTP server. If that server reaches external NTP sources over the internet, a pathway exists from the internet to OT time infrastructure. Time manipulation affects log integrity, certificate validation, sequence of events recording, and in some architectures control system behaviour. The pathway is low-consequence in isolation but undermines the integrity of the health baseline and incident forensics across the full stack.

**Derived control:** OT NTP server synchronises from an internal stratum source with no internet-facing upstream path. IT NTP and OT NTP are not the same service; the OT NTP source must be independently governed from IT infrastructure. This control is derived from the time integrity pathway, not from an NTP hardening checklist. The remediation cost is low relative to the integrity surface the pathway affects across the full stack.

**Governance state:** Required.

---

**Stage 2 status: Incomplete. Closeable: No.**

The IT/OT boundary exists physically but does not perform a consistent genuine boundary function. Several contact points remain without a stable governed position: subnet-level firewall rules with no defined service flows (S2-F1), contact points where the operator's mechanism decision is outstanding (S2-F2 through S2-F6), and boundary recovery capability with no verified procedure or named owner (S2-F7). Configuration verification is outstanding for one contact point (S2-F8). Pathway-derived controls C1 through C5 specify the active controls required at the boundary device, authenticated connections, vendor access paths, backup storage layer, and time infrastructure.

Stage 2 is not closeable while Stage 1 remains Incomplete. That condition is independent of how many Stage 2 findings reach a governed position. Stage 2 as a whole reaches Governed only when the consequence ceiling it is designed to enforce has been verified.

**Completion condition:** Stage 1 closed and verified. Every contact point identified, assessed, and carrying a stable governed position: mechanism justified against lowest-exposure alternative or accepted with named ownership and documented consequence at the appropriate consequence level. Cloud monitoring write-back capability verified at the system and governance state assigned. Boundary recovery capability verified against a defined restoration scenario with named OT recovery owner. Pathway-derived controls C1 through C5 implemented and verified at the operational systems.

---

The illustrative assessment ends here. The SOR Framework does not produce a coverage score, a maturity level, or a control inventory. It produces a decision: whether the environment can prevent unacceptable consequence, what breaks that claim, and who owns what remains.
