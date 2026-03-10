Security failures in industrial environments carry physical consequences, not merely informational ones. Architecture that cannot survive production reality does not reduce risk. It creates the illusion of it.

I design OT security architecture for high-consequence industrial environments. My work focuses on trust boundaries, identity structures, and network segmentation patterns that remain durable under operational pressure, long system lifecycles, and distributed organizational accountability.

## Context

My background runs from field automation engineering and EPCM project delivery in oil and gas and petrochemicals, through six years of operational responsibility at a SEVESO-classified PVC production facility. I currently drive enterprise OT security architecture across 14 chemical manufacturing sites in 8 European countries.

I arrived at security architecture through operations. That origin shapes how I evaluate what holds under operational pressure and what does not.

## Analysis

Structural analysis of OT security architecture, operational constraints, and failure patterns in high-consequence industrial environments

### Operational Reality

Industrial control environments operate under constraints that differ fundamentally from enterprise IT. This section examines recurring system behaviors that shape what security architectures can realistically achieve.

<p>
  <strong><a href="/analysis/why-ot-infrastructure-appears-static/" data-umami-event="click-ot-static">Why OT Infrastructure Appears Static</a></strong><br>
  <span style="color: #666; font-size: 0.95em;">Stability in continuous process industries is often an engineered response to asymmetric risk rather than technical stagnation. This analysis examines validated configurations, lifecycle economics, vendor authority boundaries, and why ignoring these constraints leads to security strategies that cannot be sustained.</span>
</p>

<p>
  <strong><a href="/analysis/silent-degradation-under-it-ot-convergence/" data-umami-event="click-ot-degradation">Silent Degradation Under IT/OT Convergence</a></strong><br>
  <span style="color: #666; font-size: 0.95em;">Redundant IT infrastructure inside segmented OT zones can degrade invisibly when health signals do not reach actors with authority to intervene. The gap is often not the absence of signals, but the absence of a clearly defined owner for acting on them.</span>
</p>

### Identity and Trust

Identity and trust architectures in OT environments operate under constraints that standard enterprise models do not anticipate. The following analyses examine how common approaches behave across segmented networks, long system lifecycles, and distributed operational authority, and where they break down.

<p>
  <strong><a href="/architecture/ot-identity-architecture/" data-umami-event="click-ot-identity">OT Identity Architecture: Federation, PAM, and Residual Risk</a></strong><br>
  <span style="color: #666; font-size: 0.95em;">A structural analysis of common identity models in OT. It explores how federation, isolation, and hybrid approaches redistribute rather than eliminate risk, and why authority for high-consequence actions must remain clearly defined.</span>
</p>

<p>
  <strong><a href="/architecture/trust-decay-in-constrained-ot-environments/" data-umami-event="click-ot-decay">Part 1: Trust Decay in Constrained OT Environments</a></strong><br>
  <span style="color: #666; font-size: 0.95em;">Certificate validation assumes trust material is continuously obtainable. In segmented OT architectures, that assumption may not hold. Trust erosion can remain latent until operational stress reveals it.</span>
</p>

<p>
  <strong><a href="/architecture/trust-flow-in-constrained-ot-environments/" data-umami-event="click-ot-flow">Part 2: Trust Flow in Constrained OT Environments</a></strong><br>
  <span style="color: #666; font-size: 0.95em;">Defines the properties required for validation to occur predictably and repeatedly inside constrained zones. Written as architectural requirements to prevent the failure modes identified in Part 1.</span>
</p>