---
title: "The Burden Map"
date: 2026-05-24
lastmod: 2026-05-24
description: "The human reality of the OT operating environment: who absorbs the security work the system produces but cannot complete."
image: "images/og-burden-map.jpg"
---

## The engineer

You know what the device is before you finish reading the alert.

It is the legacy HMI on the reformer line. It has been generating this polling pattern for years, since before the network segmentation changed, before the switch replacement changed what the network expected. You documented this in the handover notes eighteen months ago. You mentioned it in the last assessment debrief. The finding from that debrief sits in a PDF on a SharePoint that was last opened the week the consultants left.

The alert arrived at 16:43 on a Friday. You are looking at it because you are the person who looks at these. You know it is not a threat. You also know that closing it without justification will generate a follow-up from the SOC, and that the follow-up will arrive on Monday morning as an escalation, and that the escalation will require a response from your manager, who will ask you to explain it, which will take longer than explaining it now.

The justification you would need to write requires documentation that no system the SOC can access contains. The infrastructure change that produced this polling pattern was made under time pressure by a team whose mandate was delivery, not documentation. You are the documentation. You are the institutional memory of a decision made by people who have since moved on, about a device that was already legacy when they touched it. The pattern is now your Friday evening.

You close the laptop at 19:00. On Saturday morning you finish.

Nothing above you has changed. Nothing above you will.

## The chain

Step back from the desk. The situation that produced that Friday evening was assembled, over months and years, by a chain of work that never met the engineer and never will. Each layer fails in a different way. The failure modes are not interchangeable.

A consultant was engaged. The consultant arrived, ran the workshops, collected the architecture diagrams and the asset lists, and produced a findings report against a recognised framework. The report was accurate within its scope. It mapped real gaps to real controls and stopped there. When the report was delivered, the engagement closed. The consultant moved to the next client. The findings remained in the document. What happened to them was outside the scope, outside the liability, and outside the consultant's working week.

A framework defined the reference model the consultant mapped against. It was written by people who have never seen this plant, because a framework that required site-specific knowledge could not be a framework. Its authority comes from generality and its limitation is the same source. The framework cannot know which findings on this site are real risks and which are generic gaps with no operational consequence here. It describes the reference state. The distance between the reference state and this site's actual state is not the framework's problem.

A SOC provided detection coverage. The analyst who wrote the rule that fired at 16:43 calibrated it against generic OT traffic profiles because generic profiles are what a SOC managing forty clients can sustain. The analyst on shift when the alert fired had not visited this site and will be covering a different client's queue on Monday. The tuning loop that would make the rule accurate for this environment depends on local engineers feeding back false positives in time local engineers do not have. The loop is real. It runs on your evenings.

A monitoring tool generated telemetry. Coverage is the product metric because a tool that misses traffic has failed and a tool that captures everything has succeeded. The interpretation layer (which traffic patterns matter in which context given which process state on this line during this shift) is not a product feature. It requires environmental understanding the tool was not designed to produce and cannot be configured to supply.

An AI triage layer was added on top of the chain. The product claim is that the model will learn the environment over time and reduce the burden on the engineer by surfacing only what matters. The output is a generated interpretation of the alert, derived from patterns in generalised environments. It looks finished: a conclusion, phrased with the confidence of a conclusion. But the interpretive work it appears to have completed has not been completed, because the model cannot supply the environmental understanding the determination requires. Before the engineer can act on the alert, the engineer must first evaluate whether the model's interpretation is correct. The work still falls to the resolution point. What has changed is that it no longer looks like work: the residual is now concealed inside an output that presents as resolution. The validation step is new. The underlying requirement is unchanged.

A certification validated that a programme exists. The auditor checked documented controls against a standard. The controls were either documented or not. What happened between audits, in the gap between documented intent and operational reality, was outside the certification perimeter. The certificate does not certify that the controls function. It certifies that they are described within scope.

Each layer is doing what it was designed to do. The chain is functioning as specified. The chain is not neutral: it produces activity because activity is what each layer is structured to produce, measure, and bill for. None of these layers are structured to produce understanding of the facility they are operating in. They produce the appearance of understanding. Telemetry looks like knowledge. Coverage looks like comprehension. A maturity score looks like a managed security posture. A generated interpretation looks like analysis. The dashboard is legible to everyone who does not have to act on what it obscures.

## The map

What the chain transfers downward is not what it claims to deliver. The table below shows the gap, layer by layer.

| Layer | Claimed output | Actual transfer downward |
|---|---|---|
| Consultant | Risk reduction | Findings requiring specific environmental knowledge to action; a timeline that ends at delivery |
| Framework | Universal applicability | A reference state; the gap between that state and this site is unspecified and unowned |
| SOC | Detection coverage | Alerts requiring local context the SOC cannot supply; a tuning loop running on engineer time |
| Tooling | Visibility | Raw telemetry requiring environmental understanding the tool cannot supply |
| AI triage | Reduced engineer burden | Interpretations requiring engineer validation before action |
| Certification | Assurance | Evidence that controls are described; no assurance they function |

The pattern is consistent: each layer exports what it cannot complete. The residual from each layer (the gap between claimed output and actual transfer) does not disappear. It falls. It has somewhere to go.

## The position

The system selects for the person who absorbs it.

That person is defined by two properties in combination. The first is sufficient technical competence to understand what arrives. They can read the alert and know what the device is. They can read the findings report and distinguish real risks in this environment from generic framework gaps with no operational consequence here. They can translate between the language of the upstream chain (CVSS scores, framework controls, detection rules) and the language of the plant. Without this translation capability the alert is noise. With it the alert is a solvable problem, and the solvable problem becomes their Friday evening.

The second property is insufficient institutional distance to ignore what arrives. They are not protected by organisational remove. They cannot say that a particular alert is outside their remit, or that a finding belongs to a different function, or that the gap between documented posture and operational reality is someone else's problem. They know the consequences of the gaps in their specific environment. They know who gets called when something goes wrong. The institutional distance that allows upstream actors to complete a deliverable and move on is not available to them.

The combination is the structural position. Someone with less competence would not resolve the alerts. They would close them incorrectly or escalate them into noise. Someone with more institutional protection would route them elsewhere: to a team, a function, a governance process. The burden finds the person who can absorb it and cannot refuse it.

That person is not failing to manage their workload. They are correctly positioned in a system whose structure produces exactly this outcome.

The system will continue producing it regardless of how well they manage, because the workload is not the variable the system responds to. The structural position is. It is a dependency the system has never named. The Saturday morning hours are not an anomaly. They are the mechanism.

## Why the chain cannot resolve

Protection requires understanding.

Understanding of a specific facility, its actual configuration, its operational history, its undocumented dependencies and the decisions embedded in its current state, is a precondition for protection. It is not a feature that can be added to a product, scoped into an engagement, or certified into existence.

Resolution reflects this directly. Resolution is not ticket closure, finding dispatch, control documentation, or remediation planning. These are activity events. They prove that work occurred. They do not prove that the underlying security question is closed. Resolution is the point at which a specific security question in a specific operational context is no longer open to interpretation for the person who carries the consequences of leaving it open. It is an epistemic state, not a process artefact. It is also non-transferable: it cannot be packaged, outsourced, or certified, because the knowledge required to reach it lives only with the person who understands the environment well enough to know when the question is actually closed.

The upstream chain cannot supply that knowledge, because environmental understanding is not what it is designed to produce. Taken together, the chain produces artefacts. None of them produce understanding of this facility. They cannot show how it actually behaves, what has changed, or why. They remain completely blind to the undocumented dependencies between systems that no diagram has ever captured.

That mapping is the activity which would make protection possible. It is also the activity the entire upstream chain is structured to avoid, because it produces no artefact the governance model can measure. The exclusion is not deliberate. It is automatic, the consequence of measuring only what can be measured. The governance model funds artefacts. Understanding is unfunded work.

The result is a closed loop. Activity produces findings. Findings require understanding to action. Understanding lives at the resolution point. The resolution point absorbs what it can absorb with the time and capacity left after operating the plant. What it cannot absorb re-enters the activity stream as a new finding at the next assessment cycle. The loop has no completion condition. An obligation to cover everything has no boundary, so the reference state is never reached and the findings never stop. Each cycle adds outputs above the resolution point and unresolved questions at the resolution point. Each cycle deepens the system's dependency on the person who holds the understanding the system will not fund.

When that capacity is exceeded, the residual surfaces in a form the governance model misreads. Unactioned findings read as a capacity problem. Unclosed alerts read as a prioritisation failure. Neither surfaces the structural condition producing them.

The system has no resolution mechanism.

It has a distribution mechanism that routes unresolved work to the only point in the chain where understanding exists, and a measurement mechanism that converts the residue of that routing into evidence of progress.

A better-resourced programme does not change this. An embedded SOC analyst with genuine process knowledge resolves some alerts before they reach the engineer, but the analyst is themselves a resolution point, holding ungoverned environmental understanding exactly as the engineer does. A dependency distributed across a team with overlapping knowledge and a documented handover is genuinely less fragile than one held by a single engineer. But the obligation generating that volume has no boundary, and more staff does not give it one. Distributed capacity is loaded toward its limit the same way individual capacity was, over a longer interval. Programme quality changes how much burden reaches any single person and how long the arrangement holds. It does not change the structure that routes the burden. The dependency moves. Ungoverned, it does not disappear and it does not settle.

## Two readings of the same data

The system produces two realities. Both are internally consistent. Neither sees the same thing.

Management sees a dashboard. The numbers are real. They measure what the upstream chain has produced: coverage percentages, alert volumes, mean time to triage, maturity scores, certification status. Within the frame the dashboard defines, the programme is functioning. The metrics are not wrong. They are accurate measurements of the activity the chain was structured to produce.

The engineer sees something the dashboard does not contain. They see an alert that requires three paragraphs of process context to close. They see a findings report that is accurate and unactionable simultaneously. They see a generated interpretation they must validate before they can apply their own knowledge. They see the gap every time something arrives from upstream without the context required to resolve it. Within the frame the engineer operates in, the programme is exhausting. Their experience is not wrong either. It is an accurate experience of the residual the chain transfers downward.

Both views are correct within their frame. The governance model is legible to the people it reports to and illegible to the people who live in its consequences. The chain does not close the gap between facility and understanding. It makes the gap legible at one level of the organisation and exhausting at another.

When the burden becomes visible enough to reach a management conversation, the response the governance model can deploy is a training programme. The variable it can act on is the engineer. The structural position routing unresolved work to them is not something the model can see. The response targets what the model can measure. The structural condition continues.

A culture shift produces the same result by a different route: it targets collective attitudes rather than individual capability, but it leaves unchanged the structural position that routes unresolved work to the person who cannot refuse it.

The governance model positions engineers as a resource: eyes and ears on the ground, a critical sensor, the first line of defence. The framing is consistent with how the model measures everything else in the chain. Activity is produced upstream. The engineer is the point at which outputs are converted into resolution. In that frame, the engineer is not a constraint on the system. They are a function of it.

A gap that appeared in the board report would be funded. A gap that appears only in the engineer's Friday evening generates a workload conversation, a headcount request, a prioritisation discussion, another tool evaluation. None of these responses address the gap. They address the symptoms while leaving the gap in place, invisible in the metrics, comfortable at the governance level, and accumulating silently at the resolution point.

## What the system depends on

The institutional responses to the burden (more headcount, better triage, clearer escalation paths, additional tooling) produce more activity above the resolution point. They do not produce the facility knowledge required for resolution.

Instead, the activity model above the resolution point produces the appearance of control: documented findings, triaged alerts, generated interpretations, certified controls, monitored telemetry. The appearance is sustained by labour that does not appear in any of the metrics the model reports. The Saturday morning hours do not register in the maturity score. The translation work that closes the gap between generic detection and specific process context does not appear in the SOC report. The local knowledge that makes the consultant's findings actionable is contributed without being counted as a deliverable. The understanding that makes protection possible is built and maintained by the person at the resolution point, incrementally, invisibly, in the margins of a role defined as something else entirely.

The system depends on this contribution. It does not measure it. It does not credit it. It does not survive without it.

Remove the absorption and the activity model stops producing the appearance of control. What it has been producing all along becomes visible: unresolved findings, undisposed alerts, undocumented dependencies, unverified generated interpretations, the residual quietly closed by the person at the resolution point because no other resolution point existed.

The absorption failure is not always visible as heroic effort. When the engineer absorbs the burden, the work is done and the gap is closed. The system records this as nothing. The dashboard records it as nothing. The closing consumes capacity the governance model has never counted and cannot see.

When capacity is insufficient, the failure mode is different. The burden does not surface as a governance event. It surfaces as an alert closed without investigation because there was nothing left to give, a finding left unactioned because the queue never emptied, a polling pattern that warranted examination quietly marked resolved because the alternative was a Monday morning escalation that would consume more time than the investigation itself. The coverage model creates this invisibility. An obligation without a boundary never reaches a natural resolution point. Each assessment cycle produces new findings because the reference state the framework describes is never fully reached in any specific environment. The upper chain can generate indefinitely because generation is never tested against the capacity of the resolution point to action what arrives. The burden that exceeds capacity does not become visible upward. It becomes latent exposure, accumulated silently, recorded nowhere, until the pattern that was not investigated turns out to have been something other than normal.

This is not a workload problem. It is structural. The system is structured in a way that funds the appearance of understanding and extracts the substance of it from the person least protected from its consequences.

The gap is not hidden. It is structurally invisible to the people with the authority to close it, and structurally unavoidable for the person who cannot. The system is correctly aligned with what it measures. As long as it measures activity, it will produce activity. As long as activity is treated as evidence of resolution, the resolution work will continue to fall where the understanding sits, and the metrics will continue to look healthy.

## The ungoverned dependency

The structural conditions described above do not change because they are named. The system remains aligned with what it measures. The engineer is still working Saturday morning. What changes, when the position is named, is the category of the thing being described.

The engineer at the resolution point is not an overloaded employee. They are an ungoverned dependency. They carry modification capability that no other point in the chain holds: the ability to translate generic telemetry into process context, to determine whether an alert is benign or consequential, to close a question or leave it open. That capability has no named owner above it. It has no defined review condition. It has no documented consequence of loss. The organisation has never assessed the contact point between the security chain and operational reality, because the contact point is a person, and the governance model does not have a register entry for a person who functions as critical infrastructure.

When this person leaves, there is no backup of their institutional knowledge. There is no tested restore path. The understanding that makes the alerts resolvable, the history that explains the polling pattern, the knowledge of which findings matter and which do not, exists in one place and has never been required to exist anywhere else. The architecture records a green status across its dashboards because this unmapped dependency absorbs the failure rate of every layer above it. The system is running on a single leg. It is reporting full redundancy.

The dependency does not belong to the coverage model alone. A consequence-derived investment model reduces it: it externalises some of what the engineer holds into a maintained artefact, and it bounds the obligation that generates the burden. But it does not close the dependency. The mapping requires maintenance, and the person who keeps it true is the resolution point again. A corrected investment model leaves a residue, and the residue is the dependency itself: a person holding understanding the organisation has never named, owned, or made survivable. Naming it is the move this paper proposes.

This condition can be named. It can be written down as an open exposure: a dependency on unmapped environmental knowledge, held by a single unassessed contact point, with no documented owner and no verified continuity path. Written that way, it is no longer a workload complaint. The governance model does not have a mechanism for receiving a workload complaint except the ones already described, headcount and training and triage, none of which touch the dependency. The governance model does have a mechanism for receiving an exposure finding. An exposure finding requires an owner. It requires someone with the authority to fund a response or the liability to carry the risk to sign against it.

The governance model cannot see the condition as a condition, because it has no metric that registers it. It can receive an exposure finding, because an exposure finding is a category it already processes. The move does not ask the model to develop new sight. It translates an invisible structural condition into the one input format the model is built to accept, and forces it through an intake the model cannot refuse.

An exposure finding is a financial decision with a named owner and a budget consequence.

This does not reduce the burden. Visibility is not resolution. The exposure finding does not document the facility, does not build the missing understanding, does not change what arrives on Friday afternoon. What it changes is one thing only. It stops the silent downward transfer. The residual is no longer absorbed without record. The condition that produces it is named, and its ownership is placed with someone who can state the operational consequence of losing the person who currently absorbs it, or who must accept, in writing, that the consequence is unowned.

That is the entire move. It is administrative, not redemptive. Naming the dependency does not change it. It removes the ability to ignore it. The system does not become more resilient. It becomes accurately described. The engineer still works Saturday morning. What changes is that the organisation can no longer describe that condition as control.

The burden was never a workload problem. It is the shape of a system that measures activity and calls it resolution.
