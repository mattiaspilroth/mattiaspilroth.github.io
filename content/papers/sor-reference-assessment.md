---
title: "SOR Framework: Practitioner Reference"
date: 2026-05-14
lastmod: 2026-08-01
description: "A compressed reference map of the SOR Framework."
image: "images/og-sor-companion.jpg"
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
