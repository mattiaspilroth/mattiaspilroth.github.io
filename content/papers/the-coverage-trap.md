---
title: "The Coverage Trap"
date: 2026-03-29
lastmod: 2026-05-10
url: "/papers/the-coverage-trap/"
aliases:
    - /analysis/the-coverage-trap/
description: "The case that coverage-based security investment has a structural ceiling in OT environments, and what a consequence-derived alternative requires."
image: "images/og-coverage-trap.jpg"
---

Most OT security practitioners working in brownfield industrial environments reach the same point. The program is running. Controls are being deployed. Assessments are producing findings. And yet the sense that the fundamental exposures are not being addressed does not go away. Budget cycles close without the structural conditions improving. The same gaps surface in successive assessments. The practitioner working inside the environment can see that something is wrong with the investment logic, but the institutional structures around the program have no mechanism for surfacing what it is. The program is active. The exposure is not materially reduced.

This paper argues that the mismatch is structural rather than circumstantial. It is a property of the investment logic the discipline inherited, not a resourcing failure or an execution problem. Understanding that property precisely is a prerequisite for correcting it. The Sequenced OT Resilience Framework, specified in the companion document, is one instantiation of a corrected investment logic. This paper carries the argument for why the correction is needed.

Security investment in OT has produced real progress under the existing model. Controls have been deployed, gaps inventoried, and audit structures established that gave security programs organisational legitimacy they previously lacked. The practitioners who built those programs made reasonable decisions with the tools and institutional conditions available. The argument here is not that the work was misguided. It is that the investment logic those programs use has a structural ceiling in OT environments, and that correcting the investment logic is different from discarding the work.

## The Coverage Trap

The Coverage Trap is a condition in which control coverage becomes the governing unit of security investment.

Coverage measures the presence of controls. It does not measure whether those controls constrain credible pathways to consequence. The two are not the same. A program organised around coverage can expand indefinitely while remaining structurally decoupled from the conditions that determine whether consequence can be reached.

In OT environments, where controls are costly to deploy and maintain, this produces a compounding operational burden. Every control deployed adds a permanent obligation: patching, firmware maintenance, access review, alert triage, lifecycle replacement. The catalog grows. The burden grows with it.

The result is a self-reinforcing condition. The program has no defined stopping point. It cannot reach the structural gaps the catalog cannot see. The infrastructure required to sustain it becomes part of the exposure it was meant to govern.

Understanding how this condition became the default requires examining the institutional conditions under which OT security investment was first organised.

## Why coverage became the organizing principle

OT security emerged inside organisations that did not have a standing security engineering function for industrial environments. The build-operate divide left most sites without the capacity to develop contextual security models: capital projects delivered systems, operations inherited them, and neither side was structured or funded to build site-specific security architecture. When regulatory pressure arrived and the discipline needed frameworks it could specify, procure, and audit, it reached for what existed.

What was most available to procurement, audit, and program governance was IT-shaped security practice: mature control catalogs, tooling categories, maturity scoring, and evidence models that finance functions already understood. OT-specific concepts existed, but institutional implementation translated them back into coverage logic. Coverage-based compliance was the result. Given these conditions, a coverage-based model was not simply chosen. It was the only model that could be specified, procured, audited, and scaled without requiring the deep, site-specific understanding the environment actually demands. The industry conditions that produced those tools, not the judgment of the people using them, explain why the outcome was miscalibrated.

Coverage is not meaningless. Control coverage can show whether obligations were attempted, whether basic controls exist, and whether a program is producing evidence. The trap begins when coverage becomes the investment logic and is treated as a proxy for resilience.

OT-native security standards developed the right conceptual vocabulary: zones defined by function, conduits governing what crosses between them, security levels derived from consequence profile. Those concepts are correct inputs to a consequence-derived model and remain so. The critique here is not of that conceptual architecture. It is of the institutional implementation pattern that sits on top of it. Applied as catalog coverage, which is the default institutional outcome, those requirements produce a scored compliance position against a defined set of controls without the site-specific pathway assessment the conceptual architecture assumed would be performed. The standard's concepts are sound. The conditions under which the standard is applied are the problem, and those conditions are common enough to be the default rather than the exception.

The operative mechanism is the transition of practitioners into OT environments who understand framework compliance but do not have the operational depth to exercise the contextual judgment the framework assumes. Applied by someone who understands the framework structure but not the industrial environment, the implementation requirements produce coverage that is internally consistent with the standard and structurally disconnected from the site's actual consequence profile. The result is a program whose reported state and actual protection state can diverge from the outset, with no mechanism inside the model for detecting the divergence.

Coverage did not win because it was correct. It won because it was the only model that could satisfy procurement, audit, and governance simultaneously under those conditions. Given those constraints, the outcome was structurally inevitable.

## The logical failure

The coverage model is not logically sufficient to represent the protection state it is supposed to track. Protection state is the verified condition that credible pathways to consequence are constrained or terminated. A program that records deployed controls produces the same output whether those controls interrupt credible pathways to consequence or not.

Incident and absence-of-incident outcomes both confirm the model. The program has no internal mechanism for detecting divergence between its reported state and its actual protection state.

A model that is confirmed by both incident and absence-of-incident outcomes cannot function as a risk model. It is therefore not falsifiable.

The model's internal consistency can be tested directly. When an incident occurs in a high-coverage environment and the post-incident explanation remains internal to the model (a missed control, a delayed deployment, insufficient coverage), the model has absorbed the outcome without being challenged by it. If no possible outcome can force the model to revise its assumptions, the model is not describing reality. It is preserving itself.

## Why the model persisted

That logical property is part of what allowed the model to persist. Coverage was the only investment logic that could be applied without deeply understanding the target environment.

IT security operates on an assume-breach principle, where no layer can be assumed to provide protection that reduces the requirement for the next, and protecting every layer is internally consistent. That logic was transferred into OT environments whose architectural layering changes that assumption. The posture's transferability ends where that layering begins.

The institutional implementation produced coverage, and coverage persisted because it was the only form the governance structures could process.

Coverage persists because it is the only form of security that is institutionally legible. It produces artifacts that can be specified, implemented, and audited without requiring contextual judgment about the environment. That judgment does not produce the standardised artifacts institutional governance requires. Without auditability, a contextual approach cannot satisfy the institutional requirements governing security investment. That constraint is what prevented the correction mechanism from developing.

Coverage meets the structural requirements of security procurement independently of its relationship to actual protection. It can be specified in a contract, implemented by a third party, audited by a fourth, and reported to management as a percentage. Each step requires no contextual knowledge of the environment. Management visibility requires metrics. Metrics require standardised, comparable units. Control counts, maturity percentages, and gap closure rates are standardised and comparable. Whether they correlate with protection state is a question the reporting structure is not designed to ask.

That scalability made coverage commercially viable. Vendors built products mapped to control catalogs. Frameworks generated demand. Products fulfilled that demand. The market instantiated the investment logic commercially, and the commercial instantiation reinforced the framework demand. Coverage is not only an institutional logic. It is a market structure that rewards vendors for producing catalog-compatible controls and buyers for deploying them. The investment logic and the commercial infrastructure that serves it are now the same structure.

## Why it cannot correct itself

The model lacks a correction mechanism.

Audit methodology confirms that controls are present, not whether they interrupt credible pathways to consequence. The institutional structure creates an asymmetry: when the cautious choice and the contextually correct choice diverge, the structure rewards the cautious choice regardless of which better serves the environment. A practitioner who follows an established framework and later experiences an incident can point to recognised standards. A practitioner who deviates based on contextual engineering judgment carries that judgment personally. This is a structural incentive the institutional design produces, not a property of individual practitioners.

In principle, testing and post-incident analysis could provide correction. In practice, operational sensitivity limits how deeply OT environments can be tested without risking the production process. The model optimises for what can be demonstrated, not for what is structurally possible.

The model's imperviousness to correction is most visible at incident time. When a compromise occurs in an environment with a mature coverage program, the post-incident review finds that controls were in place. The maturity score was high. The audit was clean. The gap list was being worked. Coverage was not the problem. The incident is then absorbed as an implementation failure: a specific gap that was missed, a control not deployed in time, a judgment call that did not hold. Not as evidence of structural failure in the investment logic. The model survives the very outcome that should have falsified it. A model that cannot be falsified by failure is not governing risk. It is confirming itself.

The absence of correction is compounded by a structural inability to quantify the risk the program is supposed to manage. Likelihood estimates require a statistical basis that does not exist in OT security: incident data is sparse, attacker populations are heterogeneous, and the specific capability and vulnerability landscape shifts continuously. Even where past data exists, it describes a threat environment that no longer holds. Impact cannot be bounded without a defined consequence ceiling: without one, every compromise opens into an unbounded consequence space, and the assessment has no architectural basis for constraining what is reachable. The rational response to unbounded impact and unquantifiable likelihood is to treat every exposure as potentially catastrophic, which produces an unbounded control requirement. Coverage fills that vacuum. It is at least finite. Risk, without architectural bounding, is not.

Coverage persists not only because it is institutionally legible. It persists because it substitutes for a risk assessment exercise the environment structurally cannot support.

Where practitioners apply the right contextual judgment within a coverage program, the artifact does not record it. The governance output is identical whether the judgment was applied or not.

The model cannot retain or propagate what practitioners understand about their specific environment. When the practitioner leaves, the judgment leaves. What remains is the artifact, which records coverage against a catalog regardless of the quality of judgment that produced it. The institutional knowledge that would be the only basis for improvement accumulates nowhere.

Coverage measurement cannot distinguish between a control deployed through careful site-specific assessment and the same control deployed through generic catalog application. Both produce identical artifacts. Under time and resource pressure, the incentive runs toward the latter. The model does not merely fail to reward engineering judgment. It actively creates pressure against it, because judgment takes longer and produces no additional measurable output.

The training market reinforces this trajectory. Courses in framework application, tool deployment, and audit preparation are heavily subscribed because they produce skills the coverage model rewards. Courses in process operations, control system architecture, and consequence analysis are undersubscribed because that understanding does not map to the activities coverage metrics measure. The discipline trains toward its own measurement system. The practitioner population becomes progressively less equipped to identify the mismatch between coverage and protection state, because the training that would develop that capability is not commercially rewarded. Judgment does not merely leave with individual practitioners. The pipeline that would replenish it is shaped by the same incentive structure that depletes it.

Coverage programs are easy to enter because they produce immediate visible progress. They are difficult to exit because the transition replaces visible progress with structural improvement that the measurement system cannot see. During transition, the program appears to regress. Metrics stagnate or decline while exposure is being reduced. To governance structures conditioned on coverage, this appears as failure. The program must look worse before it becomes better, which creates institutional resistance to correction even when the structural problem is understood.

The practitioner making the case for a consequence-derived investment model will be asked to explain declining coverage metrics to a governance structure conditioned to treat them as progress indicators. During transition, the coverage metrics will decline. That decline is the correct signal. A program reducing its exposure position by removing unjustified connections and governing necessary ones will score lower on catalog coverage than a program maintaining all of them. The measurement and the outcome are pointing in opposite directions. That is the coverage trap, visible at the moment of correction.

## The heterogeneity problem

The lock-in compounds with the environments the model is applied to. No two sites share the same starting point, the same system connections, or the same pathway structure. That site-specificity makes exit harder: there is no standard template for what pathway governance looks like at a given site, because the pathways are different at every site.

The structural property that most consistently defeats coverage logic is site-specificity, a condition the industrial process itself produces and no framework revision can remove.

Every OT site is the product of decisions accumulated across its operational life. Underneath those decisions sits a constraint no operational choice can override: the process dictates the layout, the layout dictates the control architecture, and the control architecture determines how systems are connected, what paths exist between them, and where consequence can be reached. No two processes are identical. The specific pathways through which a compromise can reach a consequential function differ between sites even within the same industry, the same vendor ecosystem, and the same regulatory regime.

This is why coverage logic is attractive: it removes the requirement to understand site-specific connections. Apply the same controls everywhere, and the question of whether any given control is appropriate for this environment disappears. But that is also why coverage logic fails structurally. A control that is correct in one network topology can introduce the exposure it is intended to prevent in another. A firewall rule, a remote access mechanism, or a monitoring platform that reduces exposure at one site can widen the pathways to consequence at a site with different system connections and different trust relationships. The engineering judgment that coverage replaces is not optional. It is the only instrument for making that determination.

A framework cannot know the distance between its target state and where any given site actually starts. The same missing control can represent a catastrophic exposure at one site, an irrelevant artifact at another, and an already-governed dependency at a third. Percentage completion cannot represent that variance. The only valid baseline is the verified state of that specific environment, assessed against its specific pathways and connections.

## What reaches the environment and through what pathways

Once the verified state of the specific environment becomes the baseline, the central question is what can reach that environment and through which pathways.

Disruption in OT environments, whether adversarial or operational, becomes consequential through governable structures: contact points, dependencies, modification capacity, degraded recovery, and loss of diagnosability. The primary structural entry point for adversarial disruption is the boundary between IT infrastructure and OT networks. The pathway through which ransomware propagation reaches a control system is the same pathway a faulty management platform update would traverse, the same pathway a vendor session with excessive privilege would exploit, and the same dependency structure operational decay would silently degrade. Actor intent varies. The structural entry condition does not.

Operational decay is a distinct route to consequence. It does not need to enter through a boundary. It erodes the conditions that boundaries, recovery paths, redundancy, and diagnostics depend on. Degradation is not absence. It is failed correspondence between assumed state and actual state. Coverage logic that addresses adversarial threat without accounting for operational decay is missing the failure mode that operates through the same structural conditions.

The coverage model does not derive its control requirements from these pathways. It derives them from a catalog. A program that does not assess the specific contact points and dependencies through which consequence reaches a given site cannot determine whether its controls are addressing those pathways or merely populating a catalog.

## What coverage programs measure

Coverage records deployment. A firewall configured to allow all traffic is a control in place. A detection system whose alerts route to a queue that is never triaged is a control in place. A centralised backup platform with inbound credentials and write access to every protected system, and a pull-based system with device-initiated outbound transfer, both deliver backup capability. Coverage records both identically. The mechanism through which the capability is delivered, the exposure it introduces, and whether the control intercepts any credible pathway to consequence are not represented. A coverage score cannot distinguish between protection concentrated on the most critical functions and protection spread uniformly across the full surface. A site optimised for consequence and a site optimised for catalog compliance can produce identical scores.

The coverage model optimises for what can be demonstrated to a governance audience. Demonstrability favours presence over enforcement: a deployed control is visible, a constrained pathway is not. From that optimisation follows the assumption that deployment equals enforcement. The gap the score cannot represent is not that the control is absent. It is that presence and protection are not the same condition, and the coverage model has no category for the difference. Because enforcement is assumed rather than verified, measurement and protection state can diverge without the program detecting the divergence.

Coverage programs have no instrument for operational decay as a separate failure category. Decay does not present as a missing control. The control is recorded as present. What has changed is the foundation condition the control depends on. The firewall exists, but the network topology it was designed to segment has drifted. The backup system runs, but the restore path has not been validated against the current system state. The certificate authority is documented, but the certificates it issues have begun to lapse without renewal. Each control is present. Each control's effectiveness depends on a foundation condition the coverage model does not examine. Decay is not visible to coverage measurement because coverage measurement was not designed to see it.

Coverage measures what is deployed. Risk depends on what is actually constrained.

## How the compliance burden consumes the capacity to address structural gaps

Distorted measurement produces distorted allocation. Where the metric cannot distinguish between protection that is necessary and protection that is demonstrable, investment follows the demonstrable.

The protect-everything posture produces a catalog without a natural boundary. Every layer requires protection because any layer could be the entry point. Under a fixed operational budget, a catalog bounded by scope rather than by the consequence profile of the environment spreads budget and engineering capacity across the full control surface. Whether the primary failure modes have been adequately addressed remains unknown.

In OT, a control is not a one-time deployment. It is a permanent operational obligation: patching, firmware maintenance, backup verification, access review, vulnerability tracking, vendor support, alert triage, lifecycle replacement, and incident response. The catalog rewards deployment. It does not reward verification of enforced effect. Every control added extends the obligation permanently. The burden compounds with the accumulated total of everything already in place.

At scale, managing these obligations pushes programs toward centralised mechanisms: backup orchestration platforms, endpoint detection agents, centralised patch management, remote monitoring infrastructure. The function each performs, managing assets distributed across zone boundaries, cannot be delivered without crossing those boundaries. Cross-boundary access is not a configuration choice that a better implementation avoids. It is a structural requirement of the function itself. Each mechanism introduces privileged inbound access paths by design.

Beyond their individual functions, controls cease to be only protective measures. They become part of the system's attack surface, because the management infrastructure required to operate them introduces privileged pathways that would not otherwise exist. The distinction between protection and exposure is no longer categorical. It becomes a function of how the control is implemented and what pathways it introduces. This is not an anomaly of poor implementation. It is a structural property of tightly coupled systems: each component is individually justified, each interaction is individually managed, and the combined failure mode is invisible at the component level.

Coverage measurement records these mechanisms as controls. They appear on the protection side of the program's ledger while operating as contact points into the environment the program governs. The coverage metric has no category for this distinction. The program cannot detect that its management infrastructure has widened the governed exposure position, because the tools widening that position are recorded as evidence of security investment. The infrastructure required to sustain the coverage program becomes part of the exposure it was intended to reduce, and the program's own measurement confirms it is working.

One further consequence of this accounting structure is that the investment most effective at reducing the threat reaching OT does not appear in OT security budgets. Effective IT security reduces the threat population that arrives at the IT/OT boundary before any OT-side control is applied. That reduction is real and materially changes what boundary investment needs to deliver. It does not appear in OT maturity scores, OT gap lists, or OT program reviews. The result is a systematic distortion: the perceived size of the OT security problem is larger than it is for organisations with mature IT security, and investment decisions are correspondingly over-specified for the OT side and under-specified for the IT side.

The compliance burden itself consumes the capacity that would otherwise address structural gaps. Areas that fall outside compliance metrics may never be visited, not because they were assessed and deprioritised, but because recurring compliance activity consumed the available capacity. A larger team running the same model produces more coverage activity before it produces resilience.

A coverage-based program tends toward greater exposure over time, not less. The compounding burden grows as the catalog expands. The management infrastructure required to service that burden expands with it. Staff turn over and the contextual judgment they held about site-specific conditions leaves with them. The gap between reported state and actual protection state widens with each assessment cycle. The program reports improving metrics while the structural conditions that determine resilience accumulate deferred maintenance, unverified dependencies, and ungoverned exposure.

The defining property of the coverage model over time is not stagnation, but divergence.

Reported security improves while actual protection state degrades.

The system appears to be improving precisely because it is measuring a variable that is decoupled from the outcome.

The decoupling has a further consequence: it removes the signal that would otherwise create urgency. A governance structure receiving improving coverage metrics has no mechanism for determining whether the program is ahead of or behind the posture the environment actually requires. The coverage score provides a continuous sense of forward progress regardless of whether the structural exposure position is improving or deteriorating. Management is not managing risk. It is managing a score. The coverage score provides a direction of travel, not a destination. The pressure to ask whether the direction corresponds to actual improvement never develops.

A direct consequence of this structure is that risk is displaced downward in the organisation. The engineer working within the environment often understands which conditions are nominal rather than enforced, which dependencies are unverified, and which pathways remain open despite coverage metrics indicating closure. This knowledge has no representation in the governance model. It cannot be recorded, reported, or acted upon within the structures that define program success.

Management receives metrics. The engineer carries reality.

Where the model cannot represent a class of risk, that risk does not disappear. It becomes unowned. The burden shifts to the individual who can see it but cannot escalate it in a form the institution accepts.

This is why a consequence-derived model requires explicit ownership and acceptance of exposure at the management level. Without that mechanism, risk cannot move to the level where it can be governed. It remains embedded in the judgment of individuals who are neither accountable nor empowered to resolve it. That structural condition is itself a form of lock-in.

From the outside, a mature coverage program looks like progress. The audit artifacts are complete. The compliance evidence is current. The gap list is being worked. The maturity score is improving. The structural exposure is not visible through any of those instruments. The measurement increasingly measures only what is measured. The gaps that exist are never visited, and the failure remains hidden inside a reporting structure that was designed to surface it.

That hidden failure has no natural endpoint within the coverage model, because the model has no stopping point derived from consequence.

## The stopping point problem

The resource problem has no natural resolution within the coverage model because the model has no stopping point derived from consequence. The control catalog defines what must be done, but not when enough has been achieved.

Process safety engineering has a discipline for bounding investment against credible failure paths and tolerated residual risk. Relief valves, containment areas, emergency shutdown systems, and independent protection layers are each placed where they address a specific failure mode on a specific pathway to harm. Investment stops where incremental protection cost exceeds incremental risk reduction. Each barrier reduces the requirement for the next, and investment terminates where the residual risk falls within the accepted tolerance.

What is being imported from process safety is the investment logic, not the practice. The principle that barriers can be placed against specific failure modes on specific pathways to consequence, and that investment can be bounded by a consequence-derived ceiling rather than run against an unbounded catalog. The analogy does not require cyber scenarios to have process safety's data quality. It requires only that investment be placed against pathways to consequence and bounded by the protection already provided by independent barriers. The parallel extends further: a compliant safety case and a genuinely independent safety architecture are indistinguishable from the outside until an incident reveals the difference. That external opacity is not specific to safety engineering. It is a structural property of any verification model that confirms artifact existence rather than verified condition.

The coverage model has no equivalent stopping mechanism. A program built on the protect-everything posture cannot use the consequence ceiling to bound the requirement, cannot use a pathway assessment to reduce that requirement, and cannot use the architecture to establish what protection already exists at each boundary. Without a stopping point, the program cannot produce a defensible answer to whether the most important exposures have been governed. That is the condition the questions in the following section are designed to surface.

## Three questions coverage cannot answer

Three questions determine whether an environment can withstand and recover from disruption: whether access paths actually terminate in consequence rather than in catalog categories; whether safeguards are independent of the systems they protect or coupled through shared dependencies; and whether segmentation holds under real operational conditions rather than documented design. A coverage artifact alone cannot answer these questions. It was not built to ask them.

The coverage trap is not a resourcing failure. It is an investment logic failure. The protect-everything posture produces programs that over-invest in demonstrable compliance and under-invest in the structural conditions that determine whether these environments can withstand and recover from disruption. The mismatch is not visible within the governance structures that control security investment, because those structures were built to measure compliance, not resilience.

The alternative is not a better coverage score. The alternative is a different unit of analysis: the pathway by which consequence is reached, the contact point, the dependency, the modification path, the recovery assumption, and the owner who accepts what remains.

The coverage model does not fail because controls are ineffective, or because practitioners are misguided. It fails because its unit of measurement, its incentives, and its governance structures are aligned around a variable that is not causally sufficient to represent protection. Everything that follows from that alignment is internally consistent. And structurally misaligned with the outcome it is meant to produce.

## What a consequence-derived investment model requires

An investment model calibrated to these environments needs four properties that coverage logic does not natively provide.

Because the coverage model has no consequence-derived stopping point, the alternative needs **a stopping point derived from consequence:** a mechanism for determining that the most important exposures have been governed and that the remaining work sits below them in a known priority order.

Because the coverage model has no mechanism for deriving controls from pathways, the alternative needs **pathway derivation rather than catalog coverage:** controls present because a specific pathway requires them, and absences documented because no assessed pathway requires them, rather than absences recorded as gaps against a uniform catalog.

Because the coverage model has no record of what exposure the organisation has consciously accepted, the alternative needs **explicit ownership of accepted exposure:** every unresolved exposure documented, named to a responsible owner who understands what they are accepting at the level of operational consequence, and subject to defined review conditions. This is the mechanism by which risk moves from the engineer who assessed it to the manager who is accountable for it. Hidden risk becomes governed risk. The burden that practitioners carry personally under a coverage program becomes a management decision under a consequence-derived one.

Because coverage counts deployment rather than enforced effect, the alternative needs **condition verification rather than control presence:** demonstrated enforcement of the conditions that controls depend on, observed at the operational system rather than asserted in documentation.

These four properties together produce something the coverage model cannot: a defensible answer to the question of whether the investment has addressed the exposures that matter most.

## The regulatory dimension

The stopping point problem has a direct evidentiary consequence when capability-based regulatory requirements arrive. Requirements for appropriate and proportionate risk management measures, of which NIS2 Article 21 is a current example, ask whether the operator can demonstrate that risks have been identified, assessed, owned, and governed in the specific operational environment. Coverage logic does not produce the evidence designed to answer that question. It produces no record that consequence has been assessed, no defensible stopping point, and no documentation of what exposure the organisation has consciously accepted.

Regulators implementing NIS2 have generally accepted coverage-based evidence because it is the evidence available and because a consequence-based alternative has not been demonstrated at scale. A consequence-derived investment model, properly executed, produces the evidence that proportionality language calls for: pathway assessments, governed exposure records, consequence-derived acceptance decisions, and verified conditions together constitute the risk management record.

Across an industrial sector, the aggregate of coverage-based programs produces a consistent pattern: extensive audit artifacts, mature vendor ecosystems, and high compliance visibility, coexisting with largely unverified structural resilience across the population of sites. The appearance of control scales across the sector. The verification of protection does not. That gap is what proportionality-based enforcement is designed to surface.

Article 20's requirement that management bodies approve and oversee cybersecurity risk management measures is a separate accountability obligation. That requirement is not satisfied by a signature on a gap list or a maturity score. It requires that management understands what they are accepting at the level of operational consequence. A consequence-derived model produces the governance record that demonstrates that understanding, not merely the signature.

## What makes the alternative tractable

The four requirements above would be difficult to satisfy in any environment. In OT environments, three structural properties make them achievable.

Consequence varies significantly by zone. A loss of control in a safety-instrumented process and a disruption to operational support infrastructure are not the same category of event. That variance makes a stopping point derivable: once the highest-consequence exposures are governed, the remaining work sits below them in a known consequence order. The program can stop at a defensible position rather than running indefinitely against an unbounded catalog.

For process industry environments operating under functional safety regulation, the consequence ceiling is already partially constituted. The safety case defines which functions are independent and which certified protection layers bound unacceptable consequence. Where those independent protection layers hold, no control system compromise alone produces the worst credible outcome. That architectural condition converts an otherwise unbounded problem into a bounded one: the question shifts from preventing every possible consequence to governing what is reachable within a verified ceiling. Without that ceiling, every exposure analysis tends toward worst case and the investment requirement is unlimited. With it, the analysis is tractable.

OT communication patterns are deterministic, asset populations are relatively static, and legitimate traffic is predictable. A governed boundary in this environment does not need to accommodate the continuous churn that makes IT boundary governance difficult to sustain. The same structural properties that make reactive vulnerability management unmanageable make pathway governance achievable: what is known and authorised can be defined precisely, and what falls outside that definition can be identified and assessed. OT's structural constraints are not limitations to be worked around. They are the foundation a consequence-derived investment model is designed to build on.

## What follows

The Sequenced OT Resilience Framework, published alongside this paper, instantiates each of these requirements as an assessable investment sequence for high-hazard continuous process environments. The consequence ceiling provides the stopping point. Contact boundary assessment provides pathway derivation. Governed exposure mechanics enforce explicit ownership. Constraint verification, observed at the operational system, replaces presence-based confirmation. Each requirement has a structural counterpart in the framework.

A governed site operating at a consequence-derived stopping point will carry gaps against the coverage catalog. Those gaps are documented, owned, and below the threshold of material exposure. That is the correct state. The framework specification defines what it looks like.

The coverage trap is not a resourcing failure, a competence failure, or a framework failure. It is the predictable outcome of organising investment around a variable that is not causally sufficient to represent protection. That variable is control coverage. The investment logic built around it produces programs that expand their management infrastructure while leaving structural exposure ungoverned, report improving metrics while actual protection state degrades, and resist correction because the transition makes things look worse before they get better. Understanding the trap is the prerequisite for escaping it.

The difference is not in how much is done, but in whether what is done can be shown to constrain the paths through which consequence is reached.
