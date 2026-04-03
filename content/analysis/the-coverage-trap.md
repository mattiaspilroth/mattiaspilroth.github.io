---
title: "The Coverage Trap"
date: 2026-03-29
lastmod: 2026-03-29
description: "OT security programs are calibrated to demonstrate coverage rather than to address the realized threat population. The frameworks driving program design were built for environments with different failure cost structures, different change tolerances, and different threat populations."
image: "images/og-coverage-trap.jpg"
---

OT security programs are built around coverage. Coverage is measurable, auditable, and procurable. Frameworks can be specified against it, vendors can map products to it, and auditors can verify it. What coverage does not measure is whether the controls address the conditions under which these environments actually fail.

The divergence between coverage and resilience is not a recent development. It is the product of industry conditions that shaped how the discipline emerged, which frameworks it reached for, and what it was organized to demonstrate. Those conditions have not resolved.

## Why coverage became the organizing principle

OT security emerged as a discipline without a standing engineering base. The build-operate divide left most sites without a security engineering function: capital projects delivered systems, operations inherited them, and neither was structured or funded to develop contextual security models. When regulatory pressure arrived and the discipline needed frameworks it could specify, procure, and audit, it reached for what existed.

What existed was IT security. Control systems run on computers. IT security had a mature framework ecosystem, auditable control catalogs, and procurement categories that finance functions already understood. That these frameworks were built for environments with different failure cost structures, different change tolerances, and different threat populations mattered less than that they were available and that no purpose-built alternative existed to displace them. No empirically validated alternative could have been built: OT security lacked the incident data, the environmental comparability, and the lifecycle timescales required to construct one.

Coverage-based compliance was the result. Practitioners applied the tools the discipline had. The industry conditions that produced those tools, not the judgment of the people using them, explain why the outcome was miscalibrated.

## Why coverage persists: investment logic, competence gaps, and institutional reinforcement

That initial convergence persisted because coverage was the only investment logic that could be applied without deeply understanding the environment it was applied to.

IT security operates on an assume-breach principle. Assets are internet-connected, threats arrive from any direction, and no layer of the architecture can be assumed to provide protection that reduces the requirement for the next. Where breach must be assumed at every layer, protecting every layer follows as the logical response. That logic is internally consistent for IT environments.

OT framework authors faced industrial environments they could not individually characterize. A framework written for environments this varied cannot assume layering. It cannot assume that a threat reaching the control network has already crossed multiple barriers. The only posture that holds across that population without requiring site-specific knowledge is the same one IT had already developed: a protect-everything posture that specifies controls for every layer.

Coverage became the organizing principle because it is the correct response to an environment where layering cannot be assumed. The problem is not that this logic was adopted as a starting point. The problem is that it became the permanent organizing principle, applied uniformly to environments where architectural layering is real, limited in crossing points, and governable. The question the coverage model never asks is whether the boundary has been made reliable enough to change what interior investment is actually necessary.

The correction mechanism that might have interrupted this convergence was absent. IT security practitioners understood frameworks and controls but had limited exposure to the operational constraints that make long-lifecycle OT structurally different. OT practitioners understood the operational environment but rarely had the IT security depth to identify where the imported logic was a poor fit. The cross-domain competence to recognize the mismatch was not a capability the industry had developed. The discipline converged on what it could execute and audit.

The institutional structures reinforced what competence had selected. Under the coverage model, a control catalog can be specified by people who understand frameworks, implemented by people who understand the control categories, and verified by auditors whose methodology confirms that policies are written and tools are deployed. Whether those controls interrupt credible threat paths is a question audit methodology does not ask. Any approach that attempts to align with contextual reality requires judgment at every step: characterizing the site, identifying credible threat paths, assessing what the architecture already provides. That judgment does not produce the standardized artifacts that audit methodology requires. Without auditability, it cannot satisfy the institutional requirements governing security investment. Auditable artifacts and management dashboards favor the coverage model, as does the accountability structure: a practitioner who follows an established framework and later experiences an incident can point to recognized standards. A practitioner who deviates based on contextual engineering judgment carries that judgment personally.

When standards bodies eventually formalized OT security practice, they codified the coverage logic the discipline had already converged on, giving it institutional authority without correcting its calibration. The coverage model was institutionalized before the conditions for correcting it existed, not because the framework structure was wrong, but because the logic it carried was not derived from the environments it would govern. Those conditions include structural properties of OT environments that no amount of framework refinement can change.

## The heterogeneity problem

The structural property that most consistently defeats framework application is site-specificity, a condition the process itself produces and no framework revision can remove.

Every OT site is the product of decisions accumulated across its operational life. Underneath those decisions sits a constraint no operational choice can override: the process dictates the layout, and the layout dictates the control architecture. No two processes are identical. The physical process is the floor under the heterogeneity. That floor cannot be removed by framework application because it was not produced by framework gaps.

Each site's operational history continues to accumulate independently, creating a variance that grows rather than converges as unique local decisions do not replicate elsewhere.

A framework defines a target state. It cannot know the distance between that target and where any given site actually starts. Per-site assessment is not an implementation preference. It is a structural requirement that the heterogeneity of industrial environments makes permanent. A framework that cannot account for that variance has no instrument for distinguishing between a site that needs its boundary rebuilt from nothing and a site where the boundary already exists. The protect-everything posture is the only posture available to a framework in that position.

## The realized threat population

That miscalibration extends beyond architecture. The protect-everything posture inherits its threat calibration from IT, not from the conditions under which OT environments actually fail. The threat population informing that posture is not the one producing most OT incidents at standard operators (sites outside the narrow band of strategically targeted national infrastructure). The distinction matters because threat models built for that narrow band are routinely applied to operators for whom they do not hold.

Realized OT disruption at standard operators traces predominantly to IT-origin intrusion crossing inadequate boundary controls, IT compromise triggering precautionary shutdown, and operational decay accumulating without triggering corrective action. None of these requires OT-specific attack capability.

The connectivity paths that carry IT-origin threats into OT are not incidental. They are the structural consequence of IT and OT convergence: shared networks, shared management infrastructure, and business integration requirements that create paths IT-origin compromise can traverse. Where those paths exist and boundary controls are inadequate, IT-origin intrusion reaching OT is a predictable structural outcome. The operational environment is collateral, not target. The attacker frequently has no knowledge of or intent toward the industrial process. Disruption is produced by architectural proximity, not by adversary capability directed at OT systems.

Operational decay occupies a different category. It is the accumulated divergence between a system's documented state and its actual operational condition, produced without triggering the signals that would force correction. It requires no adversary and no breach. Long-lifecycle OT environments produce decay structurally: capital projects deliver systems at commissioning, operations inherits them and is funded to keep them running, and no organizational mechanism continuously verifies that documented state matches operational state. Redundant paths fail without crossing thresholds that force attention. Recovery assumptions erode while the system continues running. The environment accumulates degradation through its own internal trajectory, independent of any external action. Where boundary failures require an attacker to traverse inadequate controls, decay requires only time and the absence of verification.

Coverage programs have no category for this condition. A control can be present, absent, compliant, or deficient. Degradation occupies none of those states. The firewall exists, but the network topology it was designed to segment has drifted beyond the original design. The backup system runs, but the restore path has not been validated against the current system state. Each control is present. Each control's effectiveness depends on foundation conditions the coverage model does not examine. A program organized around control presence cannot detect foundation erosion.

OT-specific techniques are documented and the capability is real. The cost structure of developing that capability, however, concentrates it in state-sponsored operations against strategic infrastructure. OT-specific attack capability requires intimate knowledge of the target's operational architecture, control logic, and equipment configuration that is site-specific and does not transfer between targets. The incidents the industry cites as primary evidence targeted standardized infrastructure where capability investment amortizes across a comparable population. Site-specific operators do not share that property. That same site-specificity makes these operators unattractive targets for capability investment that cannot be amortized across a comparable population.

Whether or not OT-specific capability eventually reaches the standard operator population, the controls that address it are not different from the controls that address the realized threat population. They are the same controls, completed in sequence. Boundary hardening that stops IT-origin ransomware propagation is also the first barrier a sophisticated intrusion must cross. Recovery capability that survives operational decay is also the recovery capability that survives adversarial disruption. The structural foundations are prerequisites for the advanced controls, not alternatives to them. Investing in depth against sophisticated adversaries before completing those foundations does not accelerate readiness. It skips the steps that readiness depends on.

The coverage model cannot distinguish between the threat populations that are producing disruption and those that are not, because it does not derive its control requirements from the threat population. It derives them from the catalog. Where the realized threat population is dominated by boundary failures and operational decay, the protect-everything posture directs investment toward depth against adversaries that are not materializing while the conditions that are producing disruption accumulate unaddressed.

## What coverage programs measure

The inability to distinguish between these threat populations persists because coverage programs measure control presence rather than the conditions that produce resilience. That measurement carries no information about whether those controls are distributed where the potential for operational disruption is highest. The problem is not the controls. It is the investment logic that drives their selection and distribution.

Because the protect-everything posture requires controls at every layer, a coverage score records that controls exist across the estate. It cannot distinguish between protection concentrated on the most critical functions and protection spread uniformly across the full surface. A site optimized for consequence and a site optimized for catalog compliance produce identical scores.

The limitation runs deeper than distribution. Presence-based measurement has no instrument for function. A firewall configured to allow all traffic is a control in place. A detection system whose alerts route to a queue that is never triaged is a control in place. In each case the coverage score records compliance. The gap the score cannot represent is not that the control is absent. It is that presence and protection are not the same condition, and the coverage model has no category for the difference.

The limitation extends further still. A coverage program has no instrument for assessing foundation condition as a prerequisite. Controls are specified, deployed, and scored against a catalog that does not ask what the environment looks like beneath them. A site with an unknown foundation condition and a site with a verified one produce the same coverage score. The model cannot distinguish between them because it was not designed to ask.

The score is accurate. What it measures is not resilience.

## The resource problem

Distorted measurement produces distorted allocation. Where the metric cannot distinguish between protection that is necessary and protection that is demonstrable, investment follows the demonstrable.

The protect-everything posture produces a catalog without a natural boundary. Every layer requires protection because any layer could be the entry point. Under a fixed operational budget, a catalog bounded by scope rather than by the consequence profile of the environment produces a predictable outcome: budget and engineering capacity are spread across the full control surface, and whether the primary failure modes have been adequately addressed remains unknown.

Coverage programs also demand sustained operational effort to remain compliant. That requirement reflects a structural mismatch: the frameworks driving it were designed for environments where assets restart on demand, change cycles are frequent, failure cost is bounded, and centralized management infrastructure is available. In long-lifecycle OT none of those conditions hold. This obligation competes directly with production support for the same constrained resource pool, on IT timescales, without the maintenance infrastructure to absorb it. That burden includes patching, firmware maintenance, vulnerability tracking, and alert triage against detection systems calibrated to the full asset population.

The consequence is not only that structural gaps go unaddressed. The compliance burden itself consumes the capacity that would otherwise address them. Areas that fall outside the compliance metrics may never be visited, not because they were assessed and deprioritized, but because the program never stopped running long enough to reach those areas. Adding resources does not resolve this. The burden scales with the estate, not with the team. Every control added extends that obligation permanently. The burden does not grow only with new deployments. It compounds with the accumulated total of everything already in place. A larger team running the same program produces more coverage activity against the same catalog.

Executing that burden across a heterogeneous estate requires centralized management, identity, and monitoring platforms with sanctioned, high-privilege reach across architectural boundaries. In deploying these platforms, the coverage model introduces shared control planes that flatten the isolation the architecture was built around. The platforms intended to mitigate theoretical maximum exposure widen the pathways through which the realized threat population operates: IT-origin lateral movement and ransomware propagation reach OT through the same infrastructure deployed to protect it.

## The stopping point problem

The resource problem has no natural resolution within the coverage model because the model has no stopping point derived from consequence or cost. The control catalog defines what must be done, not when enough has been done.

Process safety engineering operates differently because it allocates protection against consequence-bounded failure paths, not against a control catalog. Relief valves, containment areas, emergency shutdown systems, and independent protection layers are each placed where they address a specific failure mode on a specific path to harm. Process safety investment stops where incremental protection cost exceeds incremental risk reduction. That stopping point is engineered from the consequence profile, the credible failure modes, and the protection that already exists at each layer: each barrier reduces the requirement for the next, and the model terminates where the residual risk falls within the accepted tolerance.

The logic that bounds process safety investment has no equivalent in OT security programs built on the coverage model. A program built on the protect-everything posture cannot derive an equivalent stopping point. It cannot use the consequence ceiling to bound the requirement. It cannot use the realized threat population to reduce that requirement. It cannot use the architecture to establish what protection already exists at each layer. The coverage model has no mechanism for any of these operations. The catalog ends where its authors stopped writing, not where the environment's risk profile permits.

## What the coverage model cannot provide

The coverage trap is not a resourcing failure. It is an investment logic failure. The protect-everything posture produces programs that over-invest in demonstrable compliance and under-invest in the structural conditions that determine whether these environments can withstand and recover from disruption. The mismatch is not visible within the governance structures that control security investment, because those structures were built to measure compliance, not resilience.

A different organizing logic must derive its requirements from consequence, its stopping point from architecture, and its gaps from evidence rather than from a catalog. It cannot introduce shared control planes that flatten the isolation the architecture requires. It must surface what the coverage model conceals rather than reproduce its percentage scores. The framework structure is not the problem. The organizing logic it has absorbed is. These are not properties of a better compliance framework. They are the conditions the coverage model cannot satisfy.

Where the organizing principle is coverage, the measure of progress is compliance. Where the realized threat population is misidentified and the catalog has no stopping point, compliance measures something other than resilience. Within a coverage-based model, improvement cannot converge on resilience, because resilience is not the property the model is capable of producing.

What that logic requires is the subject of a subsequent paper.
