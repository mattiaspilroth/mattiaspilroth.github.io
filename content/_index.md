Security failures in industrial environments carry physical consequences, not merely informational ones. Architecture that cannot survive production reality does not reduce risk. It creates the illusion of it.

I design OT security architecture for high-consequence industrial environments. My work focuses on trust boundaries, identity structures, and network segmentation patterns that remain durable under operational pressure, long system lifecycles, and distributed organizational accountability.

## Context

My background runs from field automation engineering and EPCM project delivery in oil and gas and petrochemicals, through six years of operational responsibility at a SEVESO-classified PVC production facility. I currently drive enterprise OT security architecture across 14 chemical manufacturing sites in 8 European countries.

I arrived at security architecture through operations. That origin shapes how I evaluate what holds under operational pressure and what does not.

## Analysis

Structural analysis of OT security architecture, operational constraints, trust models, and failure patterns in high-consequence industrial environments. The focus is on the conditions that determine whether security measures remain effective in practice, not only on the measures themselves.

### Operational Reality

Industrial control environments operate under constraints that differ fundamentally from enterprise IT. These analyses examine how long lifecycles, validated systems, segmented architectures, and operational ownership shape failure behavior and define what security measures can realistically be sustained.

<div class="article-item">
  <a href="/analysis/why-ot-infrastructure-appears-static/" class="article-link" data-umami-event="click-ot-static">Why OT Infrastructure Appears Static</a>
  <p class="article-summary">OT environments look frozen from the outside. From inside the fence, the behavior follows directly from how these systems were funded, validated, and operated. Understanding why requires mapping the constraints, because security strategies that ignore them will be overridden by them.</p>
</div>

<div class="article-item">
  <a href="/analysis/silent-degradation-in-ot/" class="article-link" data-umami-event="click-ot-degradation">Silent Degradation in OT Systems</a>
  <p class="article-summary">OT systems do not hold their commissioning state. They drift silently, without producing signals that demand correction. The ownership gaps, decayed recovery paths, and eroded diagnosability that accumulate over a system's operational life are not visible until a disruption arrives that the environment can no longer absorb. Security controls placed on that foundation inherit it.</p>
</div>

### Identity and Trust in OT

Identity and trust architectures in OT environments operate under constraints that standard enterprise models do not anticipate. The following analyses examine how common approaches behave across segmented networks, long system lifecycles, and distributed operational authority, and where they break down.

<div class="article-item">
  <a href="/architecture/ot-identity-architecture/" class="article-link" data-umami-event="click-ot-identity">OT Identity Architecture: Federation, PAM, and Residual Risk</a>
  <p class="article-summary">A structural analysis of common identity models in OT. It explores how federation, isolation, and hybrid approaches redistribute rather than eliminate risk, and why authority for high-consequence actions must remain clearly defined.</p>
</div>

<div class="article-item">
  <a href="/architecture/trust-decay-in-constrained-ot-environments/" class="article-link" data-umami-event="click-ot-decay">Part 1: Trust Decay in Constrained OT Environments</a>
  <p class="article-summary">Certificate validation assumes trust material is continuously obtainable. In segmented OT architectures, that assumption may not hold. Trust erosion can remain latent until operational stress reveals it.</p>
</div>

<div class="article-item">
  <a href="/architecture/trust-flow-in-constrained-ot-environments/" class="article-link" data-umami-event="click-ot-flow">Part 2: Trust Flow in Constrained OT Environments</a>
  <p class="article-summary">Defines the properties required for validation to occur predictably and repeatedly inside constrained zones. Written as architectural requirements to prevent the failure modes identified in Part 1.</p>
</div>