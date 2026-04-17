# Blueprint

The build layer for SSS — technical architecture decisions, product specification, pre-launch verification, and structured failure analysis for a sole founder operating an AI-powered holding company at portfolio scale.

**Author:** Sanders Software Solutions

---

## What It Does

Blueprint installs four decision-support skills that cover the full lifecycle of building a subsidiary: from choosing the right stack, to specifying the product, to verifying launch readiness, to doing a structured debrief when something doesn't land. Each skill activates autonomously based on context.

---

## Skills

### `stack-architect`
Opinionated technical decision-making for SSS's AI-first stack. Triggers whenever Martel is choosing between frameworks, databases, hosting providers, API designs, CI/CD setups, or any infrastructure component across the 10 subsidiaries. Also covers architecture reviews, tech stack questions, monorepo vs polyrepo decisions, and deploy strategies.

**Triggers:** "should I use X or Y", "what's the right database for", "infrastructure for", architecture reviews, "how should I build this"

---

### `product-spec`
Translates a subsidiary concept into a complete, buildable product specification through structured questioning. Fires when a product idea, feature set, or vague notion of "I want to build X" needs to become a concrete, actionable spec document.

**Triggers:** "product spec", "spec this out", "write a spec", "what should I build", "scope this", "define the product"

---

### `launch-checklist`
Pre-launch verification across three domains: technical readiness, legal and compliance readiness, and market readiness. Fires whenever Martel is preparing to launch a product, release a feature, go live, or ship anything to users.

**Triggers:** "launch checklist", "ready to launch", "pre-launch", "go-live", "are we ready", "ship it", "release checklist"

---

### `post-mortem`
Structured failure analysis when a launch, pitch, build, or initiative doesn't land as expected. Produces a formal debrief document with root cause analysis, what was missed, and what changes before the next attempt.

**Triggers:** "didn't work", "launch underperformed", "pitch was rejected", "failed to gain traction", "what went wrong", "post-mortem"

---

## The Build Lifecycle

```
stack-architect → product-spec → [build] → launch-checklist → ship → post-mortem (if needed)
```

---

## Installation

```
/plugin marketplace add MartelGPT10/blueprint
/plugin install blueprint
```
