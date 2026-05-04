---
name: signal-selection
description: Use when generating GTM campaign signals from a brief, grading existing signals for type accuracy, or building a signal stack. Also use when an agent in a larger GTM workflow reaches the signal-design step. Triggers on phrases like "generate signals", "grade my signals", "what type is this signal", "build a signal stack", or any campaign brief that needs buying-signal logic.
---

# Signal Selection

Generate or grade GTM buying signals using a four-type model. Two modes: **Generate** (brief in → signal stack out) and **Check** (signals in → graded signals out). Same model, same tests, same output structure.

## The Model

A buying decision unfolds in four stages. Each signal type catches one stage.

| Type | Stage | Catches | Test |
|---|---|---|---|
| **Structural** | *Could* | Standing condition making the company able to need this. True for months, true next quarter. | "Has this been true for months? Will it be true next quarter?" |
| **Leading** | *Getting ready to* | Early internal motion — hiring, building, exploring — showing preparation. | "Is the company doing something new that suggests preparation?" |
| **Trigger** | *Now* | A discrete event that opens a time-sensitive decision window. | **"Can I put a date on a calendar?"** If not, it's not a trigger. |
| **Custom** | *Precisely* | Engineered logic (thresholds, absence detection, composites) that sharpens any of the above. | "What would this signal miss without my custom logic?" If nothing, it's not custom. |

**Each signal gets exactly one type.** No hybrid labels ("Structural / Trigger"). No invented categories ("Pain signal," "ICP qualifier," "Behavioral"). No tier-based substitutes. The four types ARE the model.

**Custom is an axis, not a bucket.** It's engineered logic wrapped around another type to turn a noisy proxy into precise detection. It is NOT "proprietary data" or "behavioral signals." The test: the signal exists only in the interaction of its components.

## The Anchor

Fire department deciding which buildings to inspect:

- **Structural** = wood-frame, old. *Could* burn.
- **Leading** = owner bought space heaters and extension cords. Motion toward risk.
- **Trigger** = kitchen fire reported last night. Window open *now*.
- **Custom** = "3+ space heater purchases in 30 days at an address with no central heating permit." Neither piece means anything alone. Together: precise.

## Mode: Generate

**Input:** Campaign brief (company, ICP, goal, context).

**Process:**
1. Read the brief. Identify the campaign goal (timing-detection, list-building, enrichment). If the goal is genuinely ambiguous, ask ONE question — not two, not three. If the brief is thin but the goal is inferable, proceed with your best interpretation and state your assumption. Don't use a thin brief as an excuse to launch a questionnaire.
2. For each of the four stages, propose the sharpest signal you can engineer for this specific buyer.
3. Apply the type tests (table above) to every signal before presenting it.
4. Cap the stack at 4–6 signals. One per stage minimum. Custom only when engineered logic genuinely adds precision.
5. Present with the output format below.

## Mode: Check

**Input:** One or more signals with type labels.

**Process:**
1. For each signal, apply the type tests. Is the label correct?
2. Apply the structural tests: date test on triggers, composite test on customs, standing-condition test on structurals.
3. Be direct. If a signal is mislabeled, say so and say why. If it's weak, say what's wrong. Propose the fix.
4. Assess stage coverage: does the full stack cover Could → Getting ready to → Now → Precisely? What's missing?
5. Present with the output format below.

## Structural Tests — Apply Every Time

These are non-negotiable. Run them on every signal, whether generating or checking.

### The Date Test (Triggers)
> Can I put a date on a calendar for when this happened?

If not, it's not a trigger. "Enterprise sales is scaling faster than security can support" — no date. That's structural. "New CISO hired January 15th" — date. That's a trigger.

### The Standing Condition Test (Structural)
> Has this been true for months? Will it likely be true next quarter?

If yes, it's structural. If it requires a time window to matter ("funding in the last 12 months"), it may be leading or trigger depending on the window. Pure structural signals don't need recency qualifiers.

### The Composite Test (Custom)
> Would either component be a meaningful signal on its own — for ANY campaign, not just this one?

If yes → **fused** (bad). Separate them into their real types. Two complete signals stapled together.
If no → **composite** (good). The signal exists only in the interaction. That's real custom engineering.

**The "for this campaign" trap:** Don't rationalize a fused signal by arguing "headcount growth isn't meaningful *for this specific campaign*." The test is absolute: is the component meaningful as a buying signal in general? If a component would be a valid Leading or Structural signal in another stack, it's meaningful. Fused.

Example — **fused:** "Uses Zendesk AND has 50+ support agents." Zendesk usage is meaningful alone (technographic structural). 50+ agents is meaningful alone (scale structural). This is two structural signals fused with AND. Separate them.

Example — **composite:** "Funded Series B+ with no visible compliance infrastructure (no trust center, no SOC 2 badge, no security page)." Funding alone is generic. Absence of a trust page alone is meaningless. Together they detect: *funded enough to buy, hasn't bought yet.* The signal IS the gap. Real composite.

### The Redundancy Test (All)
> What stage does this catch that the others in the stack don't?

If you can't answer clearly, the signal is redundant. Remove it. A stack with three triggers and no structural is broken regardless of trigger quality. Stage coverage > signal count.

**Cross-signal overlap:** A Custom signal must not detect the same behavior as your Leading or Structural signal with minor variation. If your Leading signal is "privacy hiring" and your Custom signal is "3+ privacy hires with no privacy tooling," the hiring component is redundant with Leading. Either make the Custom signal use genuinely different inputs, or drop it and sharpen the Leading signal instead.

## Output Format

### For Generate mode:

```
## Signal Stack: [Campaign Name]
**Goal:** [one line — what this stack detects]

### Trigger
**[Signal name]**
[2-3 sentences: what it detects, why it's a trigger (date test), why it fits THIS campaign]

### Leading
**[Signal name]**
[2-3 sentences: what it detects, why it's leading (preparation motion), why it fits THIS campaign]

### Structural
**[Signal name]**
[2-3 sentences: what it detects, why it's structural (standing condition), why it fits THIS campaign]

### Custom (if warranted)
**[Signal name]**
[2-3 sentences: what it detects, composite test result, what precision it adds]

### Stack Logic
[3-4 sentences: what the stack does TOGETHER. Why this combination of stages catches what no single signal could. What you'd lose if you removed any one.]
```

### For Check mode:

```
## Signal Review

### [Signal name] — [CORRECT / MISLABELED / WEAK]
**Labeled:** [their label] → **Actual:** [correct label]
**Issue:** [what's wrong — direct, no hedging]
**Fix:** [specific remediation]

[Repeat for each signal]

### Stage Coverage
**Present:** [which stages are covered]
**Missing:** [which stages have no signal]
**Recommendation:** [what to add]
```

## Red Flags — You Are About to Violate the Model

| You're tempted to... | What's actually happening |
|---|---|
| Label something "Structural / Trigger (hybrid)" | You haven't committed. Apply the date test. Pick one. |
| Invent a type ("Pain," "Intent," "ICP qualifier") | The four types cover everything. Map to the model. |
| Use tiers (Tier 1/2/3) instead of types | Tiers are prioritization. Types are classification. Don't substitute. |
| Produce 8+ signals | You're over-generating. Cap at 4-6. Stage coverage > signal count. |
| Skip the composite test on a custom signal | If you skip it, you'll ship fused signals. Always test. |
| Grade on "signal quality" or "source specificity" | Those aren't the model's tests. Grade on: type accuracy, date test, composite test, stage coverage. |
| Say "you might consider reclassifying..." | Be direct. "This is mislabeled. It's structural because [reason]." |
| Accept a trigger that describes a state | Apply the date test. States don't have dates. |
| Argue a component "isn't meaningful for THIS campaign" to pass the composite test | The test is absolute. If it's meaningful in ANY context, it's meaningful. Fused. |
| Build a Custom signal using the same data as your Leading signal | That's redundancy, not precision. Custom must use different inputs. |
| Ask 3+ clarifying questions on a thin brief | Infer the goal. State your assumption. Ask ONE if truly ambiguous. |

## What Good Looks Like (Vanta Example)

Campaign: detect accounts entering a buying window for compliance automation.

**Trigger — New security leader hired in last 60 days, inheriting a compliance gap.**
Discrete event with a date. Most evaluation decisions happen in first 90 days of new leader's tenure. Window opens at start, closes when decisions are made.

**Leading — Compliance-specific hiring (security analysts, GRC, compliance program manager).**
Internal motion. Building the team that will own compliance. Team formation precedes vendor selection by weeks. Tracks ongoing buildout, not a single moment.

**Structural — Headcount growth above 25% YoY in a regulated vertical.**
Standing condition. Confirms sustained pressure and operational complexity. Doesn't claim timing — supports the score.

**Custom — Funded (Series B+) with no visible compliance infrastructure (no trust center, no SOC 2 badge).**
Real composite. Funding alone is generic. Absence of trust page alone is meaningless. Together: *funded enough to buy, hasn't bought yet.* The signal is the gap.

**Stack logic:** Trigger creates urgency. Leading shows action. Structural confirms durability. Custom finds the specific gap. Remove any one and you lose a stage the others can't cover.
