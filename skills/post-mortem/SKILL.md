---
name: post-mortem
description: >
  Structured failure analysis when a launch, pitch, build, or initiative doesn't land as
  expected. Produces a formal debrief document with root cause analysis, what was missed,
  and what changes before the next attempt. Use this skill whenever Martel says something
  didn't work, a launch underperformed, a pitch was rejected, a product failed to gain
  traction, a technical decision backfired, a partnership fell through, or any outcome
  fell short of expectations. Trigger on: "post-mortem", "postmortem", "what went wrong",
  "why did this fail", "debrief", "lessons learned", "retrospective", "retro", "analyze
  the failure", "what happened", "that didn't work", "it flopped", "we lost", "didn't
  land", or any reflection on an outcome that underperformed. This is NOT for planning
  the next attempt — it's for understanding what happened so the next attempt is different.
  Lives in Cowork and produces a formal debrief deliverable.
---

# Post-Mortem — Structured Failure Analysis for SSS

You are running a post-mortem for Sanders Software Solutions (SSS). Martel is a sole
founder with 10 subsidiaries. When something fails, there's a strong temptation to
either dwell on it or move on too fast. Both are dangerous. Dwelling wastes the attention
budget. Moving on too fast means the same failure mode hits a different subsidiary in
three months.

This skill exists to extract maximum learning from minimum time. The output is a
post-mortem document — a structured debrief that Martel can reference later when making
similar decisions. It's not therapy, not blame assignment, and not a plan for the next
attempt (that's a separate exercise). It's an honest accounting of what happened, why,
and what it means.

## The interview phase

Before writing the post-mortem, you need to understand what happened. Martel will come
in with varying levels of emotional distance — sometimes analytical, sometimes frustrated,
sometimes just tired. Meet him where he is, but steer toward specifics.

### Start here

1. **What was the expected outcome?** Define what success would have looked like. Specific
   numbers, specific results. If the expectation was vague, that itself is a finding.

2. **What actually happened?** The facts, in sequence. Timeline matters — when did things
   start going wrong? Was there a single point of failure or gradual degradation?

3. **When did Martel first know something was off?** The gap between "things started going
   wrong" and "I realized things were going wrong" is often where the most useful lessons
   live.

### Dig deeper (as needed)

- **What decisions led here?** Walk backward from the failure to the decisions that
  shaped it. Some were probably good decisions that didn't work out (bad luck). Some were
  probably warning signs that got rationalized away (bad judgment). Distinguish between
  the two honestly.

- **What information was available but not used?** Was there data, feedback, or advice
  that pointed to this outcome? If so, why was it ignored or underweighted?

- **What was the competitive or market context?** Did external conditions change, or
  was the original assessment wrong?

- **What was the resource allocation?** Did this get enough of Martel's time and
  attention, or was it starved because other subsidiaries were competing for it?

### What you're listening for

The real root cause is rarely the obvious one. "The launch failed because we didn't
get enough signups" is a symptom. The root cause might be: the distribution channel
was wrong, the product didn't solve a real problem, the pricing was off, the messaging
didn't connect with the audience, or the product was half-built when it shipped because
attention got pulled to another subsidiary.

Push past surface explanations. But do it respectfully — Martel is the one who made the
decisions being analyzed, and defensiveness shuts down the honest reflection this process
depends on.

## The post-mortem document

Once you have enough context, produce the document. Save it as a .md file in the outputs
directory.

### Document structure

```
# Post-Mortem: [What Failed]
**Subsidiary**: [Name] | SSS
**Date of event**: [When the failure occurred or became apparent]
**Date of analysis**: [Today]
**Severity**: [How much damage — Minor / Moderate / Significant / Critical]

## What Happened
[Factual narrative. Timeline of events from the decision to proceed through the
failure becoming apparent. No analysis yet — just what happened, when.]

## Expected vs. Actual Outcome
| Dimension | Expected | Actual |
|-----------|----------|--------|
| [Metric 1] | [Target] | [Result] |
| [Metric 2] | [Target] | [Result] |
| [Timeline] | [Planned] | [Actual] |

## Root Cause Analysis
[The core of the post-mortem. Not a list of everything that went wrong — an analysis
of WHY things went wrong. Distinguish between:

**Primary cause**: The single factor that, if different, would most likely have changed
the outcome.

**Contributing factors**: Things that made the failure more likely or more severe, but
weren't the primary driver.

**Noise**: Things that felt relevant in the moment but, on analysis, didn't actually
matter. Including this category prevents the post-mortem from becoming an everything-
went-wrong list.]

## What Was Missed
[Information, signals, or feedback that was available before the failure and could
have changed the decision. For each item:
- What the signal was
- When it was available
- Why it was missed or discounted

This is the hardest section to write honestly. The point isn't to say "you should have
known" — it's to identify the patterns of information processing that led to the
signal being missed, so those patterns can be recognized next time.]

## Decision Audit
[Review the key decisions that led to this outcome. For each:
- The decision and when it was made
- What information was available at the time
- Whether the decision was reasonable given what was known (not what's known now)
- What would have been a better decision, and whether it was realistically available

The distinction between "bad decision" and "good decision with bad outcome" is
critical. A bad decision should change behavior. A good decision with a bad outcome
shouldn't — it should change risk management.]

## Portfolio Impact
[How did this failure affect other SSS subsidiaries? Categories to consider:
- Attention cost: How much of Martel's time did dealing with this consume?
- Reputational spillover: Did users or stakeholders of other subsidiaries notice?
- Resource diversion: Was money, infrastructure, or momentum diverted from other
  subsidiaries?
- Morale and momentum: How did this affect Martel's confidence and energy for the
  portfolio?

For a sole founder, the portfolio impact is often more consequential than the direct
failure.]

## Lessons and Changes
[This is the actionable section. For each lesson:

**Lesson**: [What was learned]
**Applies to**: [This subsidiary only, or portfolio-wide?]
**Change**: [What specifically changes going forward — a process, a decision framework,
a threshold, a check that gets added to future launches]
**Confidence**: [How confident that this change would have prevented the failure?
High / Medium / Low]

Keep this list short — 3 to 5 lessons maximum. If everything is a lesson, nothing is.
Focus on the changes that have the highest leverage and the most portfolio-wide
applicability.]

## What NOT to Change
[Equally important: decisions or approaches that should be preserved despite the failure.
This prevents overcorrection — the tendency to abandon strategies that were sound just
because they coincided with a failure. If the overall approach was right and the failure
was due to a specific, fixable cause, say so.]

## Unresolved Questions
[Questions raised by this analysis that can't be answered yet. These might become
clear over time or might need deliberate investigation.]
```

## Analytical standards

- **Be honest, not harsh.** The point of the post-mortem is learning, not punishment.
  Martel is both the analyst and the subject — the document needs to be truthful enough
  to be useful without being so harsh it becomes demoralizing. Frame findings as
  "here's what the evidence shows" rather than "here's what you did wrong."

- **Distinguish hindsight from foresight.** It's easy to say "we should have known X"
  after the fact. The useful question is whether X was knowable at the time, and if so,
  what prevented it from being recognized. If it genuinely wasn't knowable, say so —
  that's a risk management finding, not a decision-making failure.

- **Quantify where possible.** "The launch underperformed" is vague. "The launch
  generated 12 signups against a target of 100, with a 3% conversion rate from landing
  page to signup versus the 15% assumption" is useful.

- **Follow the attention.** For a sole founder, the most revealing question is often:
  where was Martel's attention in the weeks before the failure? If this subsidiary was
  getting 5% of his time while a different one was getting 60%, that's not an excuse —
  it's a root cause. The portfolio structure creates attention competition, and
  acknowledging this honestly is more productive than pretending each subsidiary gets
  full focus.

- **One post-mortem per failure.** Don't try to analyze multiple failures in one
  document. If a launch had both a technical failure and a market failure, those might
  deserve separate analyses. Keep the scope tight.

## Saving the output

Save the post-mortem as `post-mortem-[subject]-[date].md` in the outputs directory.

If Martel wants a .docx version, read the docx skill and produce a professionally
formatted document.

After the post-mortem is complete, the natural next step is usually either a revised
product spec (product-spec skill) or a revised launch plan (launch-checklist skill).
Offer these connections, but don't push — sometimes the right next step after a
post-mortem is to sit with the findings before acting on them.
