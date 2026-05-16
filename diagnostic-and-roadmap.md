# AI OS — Diagnostic & Roadmap

This reference file is loaded when the user needs a structured assessment, a scoring rubric, or an implementation playbook. The main `SKILL.md` covers the strategic frame; this file covers the **assessment and execution mechanics**.

---

## 1. The AI-Native Maturity Diagnostic

A 5-stage rubric for locating any organization on the open-loop → closed-loop continuum. Score the user's org honestly across all eight dimensions; the lowest dimension is the binding constraint.

### Stages

| Stage | Name                  | Defining characteristic                                                                  |
| ----- | --------------------- | ---------------------------------------------------------------------------------------- |
| 0     | **Tool-User**         | AI as ChatGPT-on-the-side. No workflow integration. Productivity gain is incidental.     |
| 1     | **Copilot-Augmented** | Agents embedded in IDEs / inboxes. Open-loop. Humans still route every decision.         |
| 2     | **Workflow-Native**   | Agents own discrete workflows. Some artifacts captured. Hierarchy still intact.          |
| 3     | **Closed-Loop**       | Spec → test → agent → ship → feedback → re-spec runs autonomously. Org chart flattening. |
| 4     | **AI OS**             | Company is the intelligence layer. Humans at the edges. Token-maximized. 1000x outputs.  |

### Eight scoring dimensions

For each dimension, score 0–4 against the stage definitions above.

| Dimension                   | Probing question                                                                          |
| --------------------------- | ----------------------------------------------------------------------------------------- |
| **Information capture**     | Is every meeting, decision, and customer interaction automatically captured as data?      |
| **Spec discipline**         | Is "the spec" a versioned artifact, or does it live in someone's head?                    |
| **Test harness rigor**      | Can an agent know it has succeeded without a human looking at the output?                 |
| **Agent autonomy**          | Do agents iterate to a satisfaction threshold without human intervention each cycle?      |
| **Org topology**            | How many human-routing hops sit between customer signal and shipped response?             |
| **KPI orientation**         | Is the leadership team measuring tokens-per-outcome, or headcount-per-team?               |
| **Founder engagement**      | Does the CEO/founder personally build with agents at least weekly?                        |
| **Cultural debt**           | What % of your SOPs would have to be rewritten to function in a closed-loop world?        |

### How to use the score

- **Total ≤ 8**: Stage 0–1. Start with information capture and a single spec-driven pilot.
- **Total 9–18**: Stage 2. The org has agents but no closed loop. Skunkworks is the right move.
- **Total 19–26**: Stage 3. Push for full closure on one product line. Identify the middle layers to remove.
- **Total ≥ 27**: Stage 4. Optimize on token efficiency and DRI clarity. The leverage is now in spec quality.

The *lowest-scoring dimension* is what to fix next. There is no point scaling agent autonomy if information capture is broken — they will iterate against incomplete context.

---

## 2. The Token Maximization KPI Scorecard

For leaders ready to reframe operating metrics. Replaces traditional headcount-and-velocity dashboards.

### Primary metrics

| Metric                          | Definition                                                            | Healthy direction         |
| ------------------------------- | --------------------------------------------------------------------- | ------------------------- |
| **Monthly token spend**         | Total compute spend across all agent operations                       | Trending up, deliberately |
| **Tokens / shipped feature**    | Total tokens consumed to produce one shipped, deployed feature         | Trending down over time   |
| **Specs shipped / week**        | Number of director-authored specs that became shipped features        | Trending up               |
| **Iteration count → pass**      | Avg. agent iterations needed to pass the test harness                 | Trending down             |
| **Time-to-prototype**           | Idea → working demo. Measured in hours, not sprints.                  | <24h target               |
| **Human-routing events / week** | Times a human acted as a status messenger between two other humans   | Trending to zero          |

### Counter-metrics (warning signals)

| Counter-metric                   | What it signals                                                       |
| -------------------------------- | --------------------------------------------------------------------- |
| Token spend flat with hiring up  | Reverting to fixed-cost model — losing the AI-native posture          |
| Iteration count climbing         | Spec quality degrading; tests not capturing real customer outcome     |
| Specs/week dropping              | Director bandwidth is the bottleneck — need more authors, not coders  |
| Status meetings re-emerging      | Queryable org is breaking down somewhere                              |
| "Head of AI" hire being scoped   | AI strategy is being delegated — Founder is disengaging               |

### Reframing the "uncomfortably high API bill"

When a CFO or investor flags compute spend, the conversion is mechanical:

1. **Cost per shipped feature, AI-native** = monthly tokens × token price / features shipped
2. **Cost per shipped feature, headcount-based** = (FTE salary × team size + overhead) / features shipped
3. Run both numbers. The AI-native cost is typically 5–50x lower per shipped feature, even at "uncomfortable" token spend.

The bill is the product. Argue the unit economics, not the line item.

---

## 3. The 90-Day Skunkworks Playbook

For incumbents. Pulls a small, isolated team out of legacy SOPs to prove the closed-loop model before attempting any organizational unwinding.

### Pre-flight (Week 0)

- **Pick the AI Founder Type**: senior leader who will personally build, not delegate. Without this, abort.
- **Pick the customer outcome**: one specific, measurable customer outcome the team will own end-to-end. Not a "platform." Not a "tool." An *outcome*.
- **Air-gap the SOPs**: the team will not use the parent org's procurement, HR-driven hiring loops, ticketing systems, or review cadences.
- **Budget the variable spend**: token budget + tooling, separate from headcount budget. Leadership signs off in advance so it doesn't surface as a surprise.

### Days 1–30: Build the Queryable Substrate

- All meetings → recorded + transcribed by default.
- All decisions → captured in a single source of truth (Notion, Linear, or equivalent).
- All code → in one repo with agent read access.
- All customer interactions → routed through Pylon (or equivalent) with full transcript capture.
- **Exit criterion**: an agent can answer "what shipped, why, and what the customer thought" from data alone.

### Days 31–60: Run One Spec-to-Ship Cycle

- AI Founder Type writes the first spec personally.
- Spec includes a scenario-based test harness — what does success look like, in machine-checkable terms?
- Hand off to agents (using `gstack` commands: `/office-hours` → `/plan-ceo-review` → `/plan-eng-review` → build → `/review` → `/qa` → `/ship`).
- Measure: spec-to-deploy time, iteration count, total tokens.
- **Exit criterion**: one feature shipped, end-to-end, with no manual code authoring. Document the playbook.

### Days 61–90: Prove the Velocity Gap

- Run 5–10 spec cycles in parallel.
- Compare ship rate to the parent org's equivalent team. Capture the delta.
- Document the operating procedure: spec template, test harness pattern, agent role assignments, command protocol.
- Recruit 1–2 more Builder-Operators (NOT a manager) into the skunkworks.
- **Exit criterion**: a written, reproducible playbook + ≥10x velocity proof.

### Day 91+: Cross-Pollinate

- Present the playbook to the parent org leadership.
- Offer the skunkworks team as the **transformation chassis** — but resist any pressure to merge them back into the legacy structure.
- Identify the next product line to migrate. Skunkworks team operates as the receiving body.
- Begin the cultural unwinding **only with this proof in hand**.

### Failure modes to watch for

| Failure mode                                | Cause                                                          | Fix                                                     |
| ------------------------------------------- | -------------------------------------------------------------- | ------------------------------------------------------- |
| Skunkworks gets re-absorbed                 | Parent org demands "alignment" too early                       | Defend isolation. Cite the velocity numbers.            |
| Velocity gap never materializes             | AI Founder Type delegated the building                         | Reset. The leader must build personally.                |
| Specs are vague, agents loop forever        | Test harness doesn't capture real customer outcome             | Rewrite the harness with the customer in the room.     |
| Token spend balloons without output         | Queryable substrate isn't actually in place                    | Pause new specs. Fix the data layer first.              |

---

## 4. The Conviction Exercises (for leaders who haven't broken priors)

Conviction is generated by direct experience, not by argument. Prescribe these to leaders who are intellectually persuaded but operationally hesitant.

### Exercise 1: The 2-Hour Build

- Pick a feature the leader would have estimated at "2 weeks of engineering effort."
- Block 2 hours. Sit at the keyboard. Use Claude Code or equivalent + the gstack commands.
- Ship it to a staging environment in those 2 hours.
- **What it proves**: typing speed, sprint planning, and code review were never the limits. Spec clarity was.

### Exercise 2: The Spec Stress Test

- Take an existing in-flight feature. Read its spec.
- Now write the test harness — the machine-checkable version of "this is done."
- Notice how many things were ambiguous, missing, or unspecified in the original spec.
- **What it proves**: the org's spec discipline is the actual constraint. AI just exposed it.

### Exercise 3: The Org-Chart Walkthrough

- Take any decision that was made last week.
- Walk through every human who touched it: who routed, who summarized, who approved, who notified.
- For each step, ask: would an intelligence layer with full data have needed this human?
- **What it proves**: the middle layers were always optional. They were just the only available routing mechanism.

### Exercise 4: The Token Audit

- For one week, track every "thinking work" output (memos, decision docs, summaries, plans) the team produces.
- Calculate what those outputs would cost in tokens via an agent.
- Compare to fully-loaded labor cost.
- **What it proves**: the variable-cost model is not theoretical. The unit economics already favor it for most knowledge work.

---

## 5. Quick-Reference Diagnostic Questions

Use these as conversation openers when the user is vague or asking abstract questions. Each one surfaces a specific layer of AI OS readiness.

1. "If I gave an agent your entire org's data, could it tell me what shipped this week and why?"
2. "What's your specs-shipped-per-week? Not features. Specs."
3. "When did you, personally, last build a feature with an agent end-to-end?"
4. "How many human-routing hops sit between a customer ticket and a shipped fix?"
5. "What's your monthly token spend, and what's your fully-loaded engineering cost? Which one is bigger?"
6. "Do you have a 'Head of AI'? If yes — why isn't that you?"
7. "When was the last time you broke your own priors about what one person could build in a day?"
8. "If you fired your middle managers tomorrow, which information flow would actually break?"

The answer to any one of these tells you which layer to work on first.
