---
title: "Compliance Has a Working Range"
date: 2026-09-06
lastmod: 2026-09-06
slug: "compliance-working-range"
url: "/papers/compliance-working-range/"
aliases: []
description: "A plant run by a control system can be driven by it. Keeping the commands in the right hands is one obligation. What it can be driven to is another. The ordinary lifecycle does not ask for the second."
image: "/images/compliance-working-range.png"
---

A plant that is run by a control system can be driven by that control system. Whatever the plant can be commanded to do, it can be commanded to do by whoever holds the commands, however they came to hold them.

Two obligations follow from that, and they are usually treated as one.

The first is to keep the commands in the right hands: to manage known vulnerabilities as fixes are published for them, to separate what should not be reachable, to govern who holds credentials, and to be able to recover when something fails. This is what the discipline is organised around. It is structured by compliance frameworks, audited on a cycle, and it does real work.

The second is to establish what the plant can be driven to if the first is not enough. Not how likely a compromise is, but what becomes available when one succeeds, and whether anything stands between that and an outcome the operator cannot accept. That is not a new kind of question. It is what a safety case does, and it has been the required deliverable in major-hazard industry for decades. What is new is asking it about a compromised control system, and there the obligation is not established as a standard deliverable in the general lifecycle: not in the design review, the acceptance test, the modification procedure or the audit. Where the work is done at all it is done electively, by somebody who decided it was worth doing.

The two are not competing claims on the same budget. They work at different scopes. A programme reduces exposure everywhere, by an amount nobody can state, across a population of scenarios nobody could enumerate: somebody reaches an HMI, a historian, an alarm server, an engineering station, and the list does not close. Nothing could study them one at a time and a floor does not have to. A demonstration does the opposite. It takes one named outcome, establishes what can reach it, and establishes whether anything independent stops it, and the naming is what makes that possible, because an enumeration with no stated end never closes. One works broadly against what nobody specified. The other only works once something is specified. Neither can be run the other way.

Three positions are possible. Where every consequence a compromise can reach is recoverable and acceptable, the programme is the correct instrument and no separate demonstration is owed. Where a consequence is either unrecoverable or unacceptable, something independent of the compromise has to establish what stops it. Where the answer is not known, establishing which condition applies is what is owed first.

## What an attestation asks for

Compliance here means one specific transaction. The operator attests that specified measures are present and functioning, an assessor tests the assertion, and the deliverable is the attestation. It is not a claim about what any particular framework says about itself.

The function is to raise a floor. Somebody sets a level, everybody in scope has to reach it, and the assessor finds where they have not. Across a population that would otherwise sit wherever each operator individually decided, that is a real gain, and it is achieved without anyone having to quantify anything. It also requires the floor to be enumerable, because nobody can audit an instruction to be appropriately secure.

That is why there is a list, and the list is where the instrument's limits sit. It supplies a stopping point for each cycle and no defensible stopping point over time. Within a cycle, effort terminates when the list is complete, because the list is the object. Across cycles, nothing establishes that the list was ever the right length, because nothing in the obligation asks what the list was intended to achieve and nothing in the evidence indicates whether it achieved it. A list that is not terminated by an outcome can only grow, and nothing sizes the return on the next control either, so the decision falls to the list.

This explains behaviour that is usually attributed to indifference or to underfunding. An operator working to an attestation follows good practice as far as the plant allows and stops where operational constraint and prevailing regulatory pressure place the stop, because nothing else is available to decide it. The obligation does not say when secure is secure enough. The operator is not hoping for the best. The operator has never been told what the best would have to be.

An attestation records whether the specified obligations were met, and a clean one establishes exactly that. It is a competent instrument for the purpose. What it is not is an instrument for establishing that any constraint holds. Attested facts may become evidence inside a demonstration; they do not assemble themselves into one. The objection is not that attestations are done badly. It is that a perfect one leaves the second question untouched.

Residual risk is the missing quantity, and not because nobody writes one down. Where a framework requires it a figure is produced, compared against a tolerance the organisation sets for itself, and accepted. The decision is taken and somebody owns it. What it is taken against is a judged likelihood rather than an established bound, so what gets accepted is a number with nothing behind it: a rate nobody derived, for an event nobody characterised.

## What a demonstration asks for

A demonstration inverts the deliverable. The operator states the outcome that must not occur, produces an argument that it is prevented, and the assessor tests the argument rather than the inventory. The safety case is the established form of this in major-hazard industry, and the term is used here for the deliverable rather than for any one jurisdiction's version of it.

Measures appear in a demonstration. They appear as evidence in support of a claim, not as the claim itself, and what can be entered as evidence is constrained by what can be characterised: a physical limit, an architectural separation, a device that fails in a known direction. The difference from an attestation is not rigour and it is not cost. It is where the work stops and what stopping means. Under an attestation the work stops when the list is finished. Under a demonstration it stops when the argument holds, and if the argument does not hold, no quantity of additional control attestations closes it. The missing constraint has to be established.

This also determines what a change means. Under an attestation a plant modification raises the question of whether the control set still applies. Under a demonstration it raises the question of whether the argument still holds. The first is answered by inspection. The second occasionally requires the operator to conclude that it does not.

## Why one cannot do the other's work

A control is an item on a list: a framework requires it to be present and an assessor confirms that it is. A safeguard is something credited in a protection argument, either by carrying a figure into a calculation or by establishing a limit on what the plant can be driven to. The same equipment often answers to both descriptions. What is being claimed about it differs.

Where a safeguard is credited with probabilistic risk reduction, the credit rests on how often it fails, and how often it fails is established from history. That reasoning works where the future resembles the past, which is the case when failures arrive at random: the safeguard degrades at some rate, the demand arrives independently of the degradation, and the two coincide occasionally. The methods in use for crediting a protective measure rest on that model, whether the number is measured, conventional or inherited. A credited failure probability rests on a stated test interval, failure data for the components, an architecture, and an independence from the cause the measure is credited against. Each is a quantity somebody can check, and the credit is only as good as the weakest of them.

That model holds for the causes it was built for. Equipment degrades, operators err, and neither chooses its moment. An adversary does. Threat intelligence and observed technique are records of what has already been done, describing a population that changes in response to what defenders do. Extrapolating from them assumes a stability that the subject does not have. Under an adversary the failure and the demand are the same event, selected together by something that examined the safeguard first. The attacker chooses the moment and chooses which failure mode to use. There is no interval over which the failure is distributed, because the failure is not distributed. No quantity of operating history produces a rate for an event that is chosen rather than sampled, and no conservative constant substitutes for a rate that does not exist as a kind. Numbers of this kind can be produced and are, by judgement or by modelling. What cannot be produced is one derived from the failure model that licenses the credit, or validated against observation of the thing it describes.

None of that makes a control programme ineffective. Removing a known vulnerability removes it. Segmentation can remove or constrain reachability. Access governance removes standing credentials. Each of those reduces what an attacker encounters, and the reduction is real. What cannot be done is size it. A programme of this kind can be relied upon and it cannot be credited, and those are different claims about different things.

## The two mechanisms

A bound is a limit on what the plant can be driven to. It is a property of the plant and not of any document, and whether one exists is a different question from whether anyone has established that it does. Establishing one is consequence work of a different kind from anything the programme does. A control programme acts on the event: it limits the loss while it is happening and returns the operation to a viable state afterwards. A bound acts on the plant before any event, by establishing that the state it can be driven to is one the operator can accept. Restoration requires the harm to be reversible. A bound does not, which is why one of them reaches past the boundary and the other stops at it.

A bound holds whatever anyone elects through the pathway against which it was established. It does not depend on whether that authority was exercised by operator error, by an insider at a keyboard or by an external actor. A bound established against control-system authority does not answer for somebody with a wrench, and is not offered as one. The consequence side of it is established by ordinary process engineering. What a compromise can reach is not, and the two have to be done together, which is the part that makes the work scarce rather than the part that makes it difficult.

A control programme does two things rather than one, and the second is not preventive at all. It reduces the likelihood that a compromise succeeds: patching, segmentation, access governance. And it reduces what a compromise costs once it has succeeded: backup and restore, incident response, continuity planning, rehearsed recovery. That second half is consequence work, already inside the programme, and a substantial part of why the programme works where it works.

The programme's principal mechanism for doing it is recovery, supported by containment, response and continuity. Some of those limit the loss while it is happening and some return the operation to a prior state afterwards, and all of them require that a viable position still exists to return to or hold. Where such a position remains, the programme covers both sides of the event competently. Where none does, the consequence half has nothing to act on, because there is no restore path for a release, a rupture or an injury.

Segmentation sits across the two halves. It is bought and justified as a likelihood measure, and it also constrains what a compromise can reach, which is consequence work. Whether it does the second depends on where the boundaries were actually drawn. Boundaries drawn for operational convenience constrain reach incidentally rather than by design, and nothing in the programme establishes which kind a given site has.

Recovery breaks the pattern, because it produces evidence of its own function. A restore is attempted and it either completes or it does not, where a measure that works by preventing or detecting reports nothing when it misses. That evidence is bounded in the same direction as everything else: a restore test establishes that the restore works against the failure the tester chose, not that it works after an adversary who reached the backup chain first. Recovery is strongest where the causes are random, which is the band where the programme is the correct instrument anyway.

Which mode governs a given exposure depends on whether the consequence is recoverable and whether it is acceptable. Where it can be undone and is a loss the operation may govern as an ordinary one, unquantified reduction is a sound arrangement: being wrong about its size costs money and time, and the position is recovered. Where it cannot be undone, unquantified reduction supplies nothing to fall back on at the moment it proves insufficient. Where it can be undone but is not a loss the operation may govern as an ordinary one, the position can be restored and the obligation is still not discharged, because surviving the event afterwards was never the argument for permitting it.

That places the ordinary capabilities where they belong. Contained ransomware, a lost historian and several days of degraded operation are recoverable and acceptable, and patching, segmentation, monitoring, access governance and tested backup are the appropriate instruments for them.

The programme is legitimate and it is capped. What it governs it governs, and it may not be credited as the reason an unacceptable outcome will not occur, because the limit is in the failure model rather than in the execution.

The two obligations also recur differently. A programme runs on a calendar, because the threat environment changes continuously and controls degrade. A demonstration is invalidated by change to the plant, so it recurs when the plant is modified rather than when the year turns. Nothing requires those two questions to be put to the same review.

## Why the range has an edge

Compliance operates as an audit loop. Obligations are set, an operator attests, an assessor tests, findings are raised, and the formal cycle repeats on a period measured in years.

The loop does not act on anything that threatens the plant. It acts on the distance between the list and the estate, finding where the two have drifted apart and causing them to be brought back together. Whatever protection the listed items supply, they supply it whether or not anybody is auditing.

Three gaps are open at any moment. Somebody selected a framework, a scope and a level, and that selection fixed the target. The work against that target is never quite finished: findings stay open, remediation runs late, exceptions are carried. And the estate drifts from what was implemented against it.

Only two of those are the audit's business. The first is its premise. An operator can close every finding, carry no exceptions and have no drift on the day of the audit, and the target gap is untouched by all of it, because nothing in the cycle was ever pointed at the question of whether the target was the right one for this plant.

So compliance is not a promise that no gap exists. That residual is present immediately after a clean audit, and it cannot be sized for the same reason the reduction cannot be sized. Compliance presumes the operator can be somewhat exposed, by an amount nobody can state, for the length of a cycle.

That presumption is where the range comes from, and it is why the range has an edge at all. Can the operator survive being wrong, by an unknown margin, for the duration of a single audit cycle?

The question has a physical form that requires none of this vocabulary. Ask what restoring the system returns you to. Inside the range, time to return to operation bounds the loss: the plant comes back, the position is recovered, and the recovery time objective is the operative number. Outside it, the system still comes back and the position does not. A site that has had a release may hold a complete and tested backup set and no route back to operation, because what was lost was not the configuration. It was the plant, or the people, or the permission to run. The recovery time objective remains defined and it now measures the return of the one thing that was never in question.

Recoverable here means the operation can be returned to a position it can continue from, in a time it can carry, rather than that nothing was damaged. Where the consequence is recoverable and acceptable, the answer is yes and the arrangement is sound in aggregate. Incidents occur inside open windows, they cost money and time, the position is recovered, and the gap closes at the next cycle. Speed is not the issue: ransomware executes in minutes and the mode still holds, because what follows can be unwound.

Where the consequence cannot be undone, there is no aggregate for the loop to be right about on average. One occurrence in one open window ends the sequence, and the gap the audit eventually finds is one that has already been paid for.

There is a route out of that which does not work. An operator can state a risk, decide it is acceptable, record the decision and carry it. It requires a frequency: how often, against what the operation is prepared to tolerate. Inside the range the uncertainty can be carried, the decision is made on whatever evidence exists, and being wrong about the size of the reduction costs money and time. Outside it, the relevant frequency is the one that cannot be established, so there is no figure to accept against. What is left is to find out whether a bound already holds, and if none does, to make one hold: either by removing what lets a compromise reach the outcome, or by changing the process so the outcome is not available. Declining to look is not a third route. It is a decision to carry an exposure nobody has sized.

Survival is one limb and acceptability is the other, and the second does not turn on size. An outcome is unacceptable where the operator is not entitled to govern it as an ordinary recoverable loss, whether because of safety, environmental, legal or public obligations, or because the operation has itself placed it outside what may be traded. A fatality may be survivable for a large company in every sense a balance sheet recognises, and that does not make it an ordinary payable loss against which an uncharacterised reduction in cyber likelihood can be optimised. The same holds for a major release, and for harm that lands outside the fence on people who were party to none of it. The operation may continue after any of them. That is not the recovery the obligation is concerned with. Carrying the loss was never the available protection argument.

The criterion is not a regulatory threshold, and it is not seriousness either. Thresholds are set by inventory quantity, to allocate regulatory attention across a population of sites. They do not determine whether a consequence can be undone. A site below every reporting threshold may hold a fired boiler, a refrigeration plant charged with ammonia, or a stored quantity of a toxic gas, and the outcome available at that site is not made recoverable by the fact that no directive names it. Major accident hazard is where the criterion is most obvious, not what the criterion is. An outage of an essential service measured in weeks is not unwound by a finding raised eleven months later.

## Screening

Applying the criterion requires knowing what the exposure permits, which is what the determination establishes. That is less circular than it appears. Most of the range resolves without one, and where it does not is a describable place.

A determination establishes whether a bound exists, what it depends on, and whether it still holds in the plant as it runs rather than as it was drawn. It is finished when the answer is recorded, and it is owed where the consequence is real and not salient. That is a large population and it is not the one regulatory attention is aimed at. It includes the below-threshold site whose ammonia charge has never been thought of as a major hazard because no directive names it. It includes plant where a mechanical protection was credited decades ago and has never been tested against a pathway that did not exist when it was installed. It includes any site where the honest answer to what the control system can drive the process into is that nobody has looked.

Existing continuity work assists the first screen. Setting a recovery time objective requires knowing what an outage costs, which is a consequence determination that no framework treats as controversial. A number derived from what the operation can absorb, rather than from what the systems can restore, will sometimes show that the consequence is not recoverable at all.

The condition in which nobody has looked is the common one, and it is a fact about the lifecycle rather than about operators. Hazard studies examine control failure as a cause of deviation, case by case, and they are required at design and at modification. What they do not ordinarily assemble is the full range of states the control system can command, taken together and treated as a property of the system rather than as an input to one scenario. The question has no owner, so it has no answer, and its absence is invisible because nothing reports on it.

At the two ends of the range, screening is free and it resolves in a sentence. A chlorine store or a fired heater resolves immediately, and the operator holding one already knows it, usually from a hazard study written for entirely different reasons. A conveyor line, a packaging hall or a distribution warehouse resolves as fast in the other direction: the worst available outcome is stopped production and an expensive week, nothing is unrecoverable or unacceptable, and compliance is the correct and complete instrument for the cyber consequences available there. No demonstration is owed there and none should be sold.

Neither end is decided by how dangerous the site is. A single-train plant whose only compressor carries an eighteen-month lead time resolves outside the range with no hazard involved at all. Nothing about that outcome is dangerous and nothing about it is permanent. The operation does not survive eighteen months of not running, and a compliance programme has nothing to offer against it, because what would be needed is a limit on what a compromise can do to that machine.

## The pathway is chosen for convenience

Consequence depends on how far a single compromise travels, and that distance is set by architecture rather than by control coverage.

There is no rule requiring a metrics collector to reach every system on a site with high privilege. That deployment is chosen because it is faster to build, simpler to maintain and quicker to hand over. The same logic produces flat administrative domains and remote access arrangements scoped to whatever was convenient at the time. None of these decisions is careless. Each is the efficient answer to the question that was actually asked.

This is how a capability appropriate inside the working range reaches beyond it. Monitoring and backup are the right instruments for a recoverable consequence. Monitoring and backup delivered as site-wide privileged infrastructure are also a pathway, and nothing about the range they were bought for constrains where they reach.

Convenience selects the architecture, and the architecture determines how far a single compromise travels. As production and information systems couple more tightly, that distance grows, and nothing in an attestation asks what any of these components can reach.

## What is offered instead

The standard explanation for the minimum is that the money is not there. Sometimes it is, and where the binding constraint is engineering hours rather than budget that is a real constraint and a different one. But two kinds of deferral are being confused, and only one of them is about cost at all.

Informed deferral is a stated risk, an assessed consequence, and a documented decision to accept it for now, revisited on a cycle. Major-hazard operators do this routinely, with capital backlogs that everyone can size and nobody can fund at once. That is risk management working under constraint.

Default deferral has no assessment, therefore no stated risk, therefore nothing to decide against, therefore nothing happens. No decision was taken, because there was never a decision in front of anyone. The two look identical in the installed plant. The certification artefact is what permits the confusion: it carries a date, a signature and a reference to an obligation, and it has the appearance of a risk decision without obliging anyone to state a consequence or accept one.

The obvious response is that the discipline should stop treating this as compliance and start treating it as a business risk, actively managed, owned and reviewed. Moving it onto a register does not close the gap. The entry closes nothing unless it states the consequence, identifies how a compromised authority can reach it, and records what independent protection remains. A register can hold the result of a determination. It cannot substitute for one.

Attention is not the missing ingredient. The missing ingredient is a deliverable that can fail. An attestation can be incomplete. A rating can be disputed. Only a demonstration can be shown wrong.

## This correction has been made before

An adjacent discipline has already run this experiment and published the result.

Offshore oil and gas in the United Kingdom was governed before 1988 by a prescriptive regulatory regime, mandatory, inspected and enforced, administered by a department that was also responsible for production. The public inquiry into the Piper Alpha disaster, led by Lord Cullen, reported in November 1990. What followed changed the required deliverable: from conformity with prescription, to an argument by the duty holder demonstrating control of the hazard. Compliance with a list of requirements had not been equivalent to control of what the list was written for.

The correction was structural. Safety regulation transferred to the Health and Safety Executive, separating it from the department responsible for offshore operations, and the Offshore Installations (Safety Case) Regulations 1992 replaced prescription with a goal-setting obligation. Every duty holder had to submit a safety case for acceptance, identifying the major accident hazards and demonstrating that the risks arising from them were as low as reasonably practicable. From 30 November 1995 it was unlawful to operate an installation on the United Kingdom continental shelf without one. The same logic sits under the Seveso directives and the process safety regimes governing major-hazard sites onshore today.

The relevant point is not Piper Alpha. It is that a sector established that its governance mode was outside its working range, identified the mismatch precisely, and changed the mode. Thirty-six years after Cullen reported, operational technology security still relies on the same kind of instrument in cases presenting the relevant problem: conformity with specified measures does not establish that an unacceptable outcome is bounded. The recurrent response is to ask whether the list should be longer or its enforcement firmer.

The mode has since transferred to security. The Office for Nuclear Regulation moved nuclear security regulation to an outcome-focused basis in 2017, covering cyber security alongside physical and personnel security and deliberately aligned with the non-prescriptive safety regime beside it. Dutyholders are not issued a checklist. They submit security plans, and those plans are assessed against principles. It is not a safety case for cyber security and should not be described as one, it has required continuous regulatory work in the nine years since, and what it required was not a longer list.

## What the deliverable would be

State the outcome that must not occur. Identify the pathways by which a compromise reaches it. Establish that those pathways are bounded by something that does not itself depend on the compromised system. Test the bound, record the result, and repeat when the plant changes.

Independent means the thing supporting the bound does not depend on the authority assumed compromised: being a different product, a different network or a different supplier does not establish it.

What the bound has to hold against is a single compromise, not the absence of consequence. A single compromise means one authority, used once or used repeatedly in a single sequence with nothing independent of it intervening. The unit is the authority rather than the command or the actor: once acquired, it does not have to be acquired again for each command issued through it. The question is how far that authority reaches before something independent intervenes.

That is four sentences and it is the whole obligation. It is answerable at any scale. A large operator answers it at greater effort than a small one, which is an argument for requiring it there rather than for substituting a control programme in its place. Scale changes the difficulty of the answer. It does not dissolve the question.

It is not a risk assessment and it is not a remediation programme. Bounding a consequence produces an envelope, not a position: it establishes what the plant can be driven to, not how likely anything is. Exposure and likelihood remain worth assessing inside that envelope, using the methods and evidence already established for the plant's ordinary causes. Consequence is sequenced first because it is the axis on which information exists, and because it determines which consequences are available to a single compromise at all. What follows from an adverse result is the operator's decision, taken with the same people who decide every other capital question at the site.

The assessment terminates. What it uncovers may not. Declining to look does not remove the exposure. It leaves the operator unable to say whether a capital decision already exists, and leaves the timing of that decision to the event.

The demonstration is not a permanent second programme running alongside the first. It answers a question once, and again when the plant changes. What it does in between is resize the band that the control programme is responsible for.

A bound does not make a compromise consequence-free. It limits what the compromised authority can reach, so that what remains is recoverable and acceptable.

Where the answer is that the bound holds, everything still available to a compromise falls inside the range the operation can recover from and may govern as ordinary loss, and the compliance programme is then operating in the mode the case requires. Not tolerated. Correct. What remains open is narrower and does not reopen the mode question: whether the programme's own delivery introduces reach that the bound did not assume.

A plant with hardwired interlocks, mechanically constrained final elements, or protection that does not depend on the systems a compromise would reach may already be bounded, by engineering carried out long before anyone considered a cyber pathway. The engineering does the work regardless of why it was done. What the operator lacks in that case is not protection. It is the statement, and everything that follows from having one: the ability to credit it, to test it against the next modification, and to say what the security programme is and is not responsible for.

The three results a determination can return are not symmetrical in cost. An established bound costs an assessment and buys a defensible position. An absent one requires change and may require capital. One that cannot be determined either way leaves the operator facing a decision about whether to spend more on determining it. No operator can know which of the three they face without asking.

## Who receives it

A demonstration requires an assessor competent to evaluate it. That is the binding constraint, and nothing here resolves it.

A goal-setting regime works where the body receiving the argument can test it, and collapses back into attestation wherever it cannot. The European position illustrates the failure mode. The obligation under NIS2 is stated in goal-setting terms, requiring measures appropriate and proportionate to the risk. What reaches the operator can be a control list all the same, produced by national transposition, by assessors who need something determinate to test against, and by a market that sells against enumerable requirements. Determinacy is demanded from below, and it is granted, because the alternative is a regime nobody can administer.

The nuclear case shows what refusing that demand costs. It required a regulator to build and maintain the competence to receive an argument rather than an inventory, and the burden is not only on the assessor: that transition was requested by the regulated population and still took years.

Competence of this kind is built by doing. The population able to evaluate a demonstration is made out of the people who have produced and reviewed them, which means the constraint resolves from the operator side before it resolves from the regulatory side. Where it begins is where the consequence is already recognised, the hazard is already documented, and an authority already receives an argument about it. That is a small population, and it is the one that would have to move first.

That population is further along than the rest. Where a site holds instrumented protection, the functional safety standards already require something in this territory: that the independence of a credited function be accounted for, and that the security risks reaching it be assessed. And a receiving body already exists, in the assessment that examines whether a lifecycle was executed rather than whether an inventory is complete. So the obligation is not absent there. It is present, scoped short of the question, and discharged by a review that asks whether the function is protected rather than whether the credit it carries survives what reaches it. That is a different failure from the one everywhere else, and it is the more tractable of the two.

There is a precedent for building the rest. Functional safety assessment as a defined lifecycle activity, with a competence requirement attached to it, is a creation of the standards. The certification schemes that qualify people to perform it came afterwards, and the form the argument takes was worked out over years, because a requirement existed and somebody had to be able to receive it. The requirement came first there. Here it has not.

## What is missing

Methods are not the missing part. Consequence-first work exists in operational technology. Consequence-driven Cyber-informed Engineering, developed at Idaho National Laboratory, begins from the outcomes an operator cannot tolerate and works back to what would have to be engineered out. Cyber process hazard analysis takes the deviation structure of a process hazard study and admits compromise as an initiating cause. Civil nuclear operates outcome-focused regulation covering cyber.

None of this changes the general position, and the reason is not that the methods are inadequate. Across most of operational technology no general obligation requires a consequence demonstration, no settled function receives one, and no common lifecycle rule invalidates the result when the plant changes. An operator may never have heard of any of these methods without breaching anything.

This mode of governance is mature. It is taught, and it is mandatory in industries that decided some decades ago that lists were not sufficient for cases of this kind. In operational technology the nearest obligations stop short of the question, and the assessments that receive them are not looking for the answer. The instrument exists. The obligation does not reach it.

---

*How an operator establishes what a given system can reach, and the order in which that work is done, is specified in <a href="/papers/sequenced-ot-resilience/" class="article-link-text" data-umami-event="click-chwr-sor">Sequenced OT Resilience Framework</a>. Why an individual control cannot be sized on the likelihood axis, and what one costs to apply rather than to buy, is treated in <a href="/papers/control-nobody-argues-about/" class="article-link-text" data-umami-event="click-chwr-cnaa">The Control Nobody Argues About</a>. One arrangement in which a bound is credited and not established, and what the calculation requires of anyone who wishes to retain it, is worked through in <a href="/papers/independence-cannot-be-discounted/" class="article-link-text" data-umami-event="click-chwr-icbd">Independence Cannot Be Discounted</a>.*