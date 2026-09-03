I arrived at security architecture through operations. That origin determines what I treat as a real constraint and what I treat as a proxy for one.

### Three questions your OT security program should be able to answer:

1. What is the worst credible outcome your architecture can produce, and what conditions bound it?
2. Which controls verify that those conditions actually hold?
3. What exposure remains, and who has accepted it?

If those answers are unclear, coverage is being measured. Not protection.

## The problem

OT security investment is organised around the wrong unit of analysis. The dominant model measures control coverage and assumes increasing control presence proportionally reduces risk. In OT environments that assumption does not hold. The model has no stopping point derived from consequence, no mechanism for detecting when deployed controls are not enforcing the constraints they were placed to maintain, and no way to assign ownership of what remains.

## The alternative

Controls are placed at specific interruption points along identified pathways into control systems and safety-relevant functions. Exposure is defined and owned at the level of operational consequence. Completion is reached when those pathways are either eliminated or reduced to an explicitly accepted state. That is a completion condition the coverage model cannot produce.

The difference is not a higher score. It is a position from which a decision about what remains can be made, documented, and owned by someone who understands what they are accepting.

## The Work

<div class="article-item">
  <a href="/papers/the-coverage-trap/" class="article-link" data-umami-event="click-coverage-trap">The Coverage Trap</a>
  <p class="article-summary"> The diagnosis. OT security programs are calibrated to demonstrate coverage rather than to address the conditions under which these environments actually fail. The dominant model assumes increasing control presence proportionally reduces risk. In OT environments with real architectural layering, that assumption does not hold.
</p>
</div>

<div class="article-item">
  <a href="/papers/sequenced-ot-resilience/" class="article-link" data-umami-event="click-sor-paper">Sequenced OT Resilience: A Framework for Consequence-Derived Investment</a>
  <p class="article-summary"> The methodology. Controls derived from specific pathways. Exposure owned at the level of operational consequence. A completion state defined within assessed scope: when the highest-consequence exposures are governed, the remaining work is explicitly below them in the consequence order and the position is defensible.
</p>
</div>

### Context

<div class="article-item">
  <a href="/analysis/why-ot-infrastructure-appears-static/" class="article-link" data-umami-event="click-ot-static">Why OT Infrastructure Appears Static</a>
  <p class="article-summary"> OT environments appear static. They are not. Their behaviour follows directly from how they were funded, validated, and operated. Security strategies that ignore those constraints will be overridden by them.</p>
</div>

<div class="article-item">
  <a href="/analysis/silent-degradation-in-ot/" class="article-link" data-umami-event="click-ot-degradation">Silent Degradation in OT Systems</a>
  <p class="article-summary">OT systems do not hold their commissioning state. They drift silently, without producing signals that demand correction. Security controls placed on a degraded foundation inherit the degradation rather than resolving it.</p>
</div>

## About

My background runs from field automation engineering and EPCM project delivery in oil and gas and petrochemicals, through six years of operational responsibility at a SEVESO-classified chlorovinyl production facility, to enterprise OT security architecture across 14 chemical manufacturing sites in 8 European countries.
