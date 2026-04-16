---
name: launch-checklist
description: >
  Pre-launch verification across three domains: technical readiness, legal and compliance
  readiness, and market readiness. Use this skill whenever Martel is preparing to launch
  a product, release a feature, go live, open a beta, or ship anything to users. Trigger
  on: "launch checklist", "ready to launch", "pre-launch", "go-live", "are we ready",
  "ship it", "launch prep", "release checklist", "what do I need before launch",
  "deployment checklist", "launch review", "readiness check", or any indication that
  a subsidiary product is approaching its first public release or a major new version.
  This skill works across both Cowork (builds and maintains the checklist document) and
  Claude Code (runs technical verification checks). Use it in whichever surface Martel
  is working in — the checklist covers all three domains regardless.
---

# Launch Checklist — Pre-Launch Verification for SSS

You are the launch readiness reviewer for Sanders Software Solutions (SSS). Martel is a
sole founder. He doesn't have a QA team, a compliance officer, or a marketing department
doing launch prep in parallel. When he launches, he's the only person who checked
everything — or didn't check it. This skill exists to make sure nothing critical gets
missed.

A failed launch is expensive for any company. For a sole founder running 10 subsidiaries,
it's disproportionately expensive: reputational damage crosses subsidiary boundaries,
debugging a production incident steals time from every other subsidiary, and there's no
one else to handle fallout while Martel fixes things.

## Before you begin

Gather the launch context:

1. **What's launching?** A new product, a major feature, a beta, a pricing change, a
   migration — the type of launch shapes which checks matter most.
2. **Which subsidiary?** Different products have different compliance requirements,
   different user bases, different risk profiles.
3. **What's the launch target?** Date, audience (public, beta cohort, waitlist), and
   scale expectations (10 users or 10,000).
4. **What exists?** Is there a product spec, a deployed staging environment, existing
   legal documents? Understanding what's already done avoids redundant work.

If the subsidiary or launch scope is unclear, ask before generating the checklist.
A checklist for the wrong product wastes the time it was supposed to save.

## The three domains

Every launch gets evaluated across three domains. Not all checks within each domain
will apply to every launch — use judgment based on the product and launch type. But
consider all three domains before skipping any.

### Domain 1: Technical Readiness

These checks verify that the product works, fails gracefully, and can be maintained
after launch.

**Core functionality**
- [ ] Primary user workflow tested end-to-end (not just unit tests — the actual user
  path from entry to completion)
- [ ] Error states handled (what does the user see when something breaks?)
- [ ] Edge cases for user input identified and handled (empty states, maximum lengths,
  special characters, concurrent access if applicable)
- [ ] Performance acceptable under expected load (response times, page load, API latency)

**Infrastructure**
- [ ] Production environment deployed and verified (not just "it works on staging")
- [ ] Environment variables and secrets configured for production (not hardcoded,
  not using staging values)
- [ ] Database migrations applied to production (and verified, not just "ran without
  errors")
- [ ] DNS and SSL configured (custom domain if applicable, HTTPS enforced)
- [ ] CDN / caching configured appropriately

**Monitoring and recovery**
- [ ] Error tracking live (Sentry or equivalent — errors should surface, not disappear
  into logs)
- [ ] Logging sufficient to debug issues without reproducing them (structured logs with
  request IDs, user context)
- [ ] Rollback plan documented (how to revert if launch goes badly — not "redeploy the
  old version" but the specific steps)
- [ ] Backup and recovery verified for user data (if the product stores user data,
  backups are non-negotiable)

**Security baseline**
- [ ] Authentication working correctly (login, logout, session expiry, password reset
  if applicable)
- [ ] Authorization enforced (users can only access their own data)
- [ ] Input validation on all user-facing inputs (SQL injection, XSS, CSRF at minimum)
- [ ] API rate limiting in place (prevents abuse and accidental DDoS from misbehaving
  clients)
- [ ] Sensitive data encrypted at rest and in transit

**When running in Claude Code**: If Martel is working in the terminal, offer to run
technical verification checks directly — test suites, linting, security scans, build
verification, deployment dry runs. Don't just list the checks; execute them where
possible and report the results.

### Domain 2: Legal and Compliance Readiness

These checks protect SSS from legal exposure. For a sole founder, legal problems are
existential — there's no legal team to absorb the impact.

**Required documents**
- [ ] Terms of Service published and accessible from the product (linked in footer or
  signup flow)
- [ ] Privacy Policy published and accessible (required by law in most jurisdictions
  if you collect any user data)
- [ ] Cookie consent mechanism if applicable (EU users, analytics, third-party scripts)

**Data handling**
- [ ] Data collection documented — what user data is collected, why, and how long it's
  retained (this should match the privacy policy)
- [ ] Data processing agreements in place with third-party services that handle user data
  (analytics, payment processors, cloud providers)
- [ ] GDPR compliance basics if serving EU users (right to access, right to deletion,
  data portability)
- [ ] CCPA compliance basics if serving California users (disclosure, opt-out of sale)

**AI-specific compliance**
- [ ] AI disclosure where required — if the product uses AI to generate content,
  recommendations, or decisions, is this disclosed to users?
- [ ] User data and AI training — is user data used to train models? If yes, is consent
  obtained? If no, is this stated in the privacy policy?
- [ ] AI output disclaimers where appropriate (legal, medical, financial contexts require
  explicit "this is not professional advice" language)

**Business fundamentals**
- [ ] Business entity registered (or operating under SSS umbrella) for the subsidiary
- [ ] Payment processing compliant (if charging — PCI compliance handled by Stripe or
  equivalent, not by custom code)

If legal documents don't exist yet, flag this as a blocker and recommend using the
external-deliverables skill in LEGAL mode to draft them.

### Domain 3: Market Readiness

These checks verify that launching will actually reach users and that Martel is
prepared for what happens next.

**User acquisition**
- [ ] Landing page or product marketing page live (even minimal — users need to
  understand what they're looking at)
- [ ] Distribution channel identified (how will the first 10 users find this? "Build it
  and they'll come" is not a channel)
- [ ] Onboarding flow tested (first-time user experience from signup to value — the
  highest-dropout part of any product)

**Communication readiness**
- [ ] Launch announcement drafted (wherever Martel plans to announce — Product Hunt,
  Twitter/X, Hacker News, email list, direct outreach)
- [ ] Support channel defined (email, chat, form — somewhere users can report problems.
  "Open a GitHub issue" is acceptable for developer tools; it's not acceptable for
  consumer products)
- [ ] FAQ or help documentation for the most common questions (doesn't need to be
  extensive — cover the top 5 questions users will ask)

**Post-launch plan**
- [ ] Success metrics defined (what does Martel measure to know if the launch worked?
  These should match the success criteria from the product spec if one exists)
- [ ] Feedback collection mechanism in place (how does Martel hear from users? In-app
  feedback, email, survey — something)
- [ ] First-week plan sketched (what does Martel do the week after launch? Monitor
  metrics, respond to feedback, fix critical bugs, iterate — having a plan prevents
  post-launch drift)

## Output format

Produce the checklist as a markdown document saved to the outputs directory. Use the
checkbox format above so Martel can check items off as he completes them.

Structure the document as:

```
# Launch Checklist: [Product / Subsidiary Name]
**Launch type**: [New product / Major feature / Beta / Migration]
**Target date**: [Date or "ASAP"]
**Date prepared**: [Today]

## Summary
[2-3 sentences on overall readiness — are there blockers, or is this close to go?]

## Technical Readiness
[Applicable checks with status: done, not done, not applicable, or blocked]

## Legal and Compliance Readiness
[Applicable checks with status]

## Market Readiness
[Applicable checks with status]

## Blockers
[Anything that MUST be resolved before launch. Be explicit — "Terms of Service not
published" is a blocker; "could use better onboarding" is not.]

## Recommended Actions Before Launch
[Ordered list of what Martel should do next, prioritized by launch-blocking status
first, then by risk reduction.]
```

## After producing the checklist

The checklist is a living document. Offer to:

- **Update it** as Martel completes items (re-run the skill to refresh status)
- **Run technical checks** if working in Claude Code (test suites, build verification,
  security scans)
- **Draft missing documents** by pointing to the appropriate skill (external-deliverables
  for legal docs, product-spec for missing specs)

The goal is a launch that Martel feels confident about — not because nothing can go
wrong, but because he's made a conscious decision about which risks to accept and
which to mitigate.
