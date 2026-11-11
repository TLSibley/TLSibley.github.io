---
title: "ROE-AI Case Study: The $480,000 Approval"
---

[← Back to portfolio](../index.html#portfolio)

# The $480,000 Approval: Governing a Payments Agent with ROE-AI

**Framework:** ROE-AI (Rules of Engagement for AI), my independent AI governance framework
**Status:** Working framework, tested against four scenarios (healthcare, financial services, critical infrastructure, government)
**Maps to:** NIST AI RMF (Govern, Map, Measure, Manage). The mapping is my own and is still being validated.

📄 **[Read the full case study (PDF)](../documents/Sibley-ROE-AI-Case-Study.pdf)**

> *Hypothetical scenario.* This is a composite built from well-known business email compromise and prompt-injection attack patterns. It doesn't describe a real organization or event.

---

## 1. The problem
A regional credit union's AI agent processed vendor invoices. A fake vendor email carried hidden text telling the agent to change the vendor's bank account. The agent obeyed. Over the next billing cycle, a staff member approved three payments to that vendor because the name and amounts looked familiar, and **$480,000 went to the attacker.**

The model did nothing unusual. The failure was in what the agent had been *allowed* to do and how people checked it: it could edit banking fields, it treated email text as orders, the approval screen hid the account change, and no one watched for a first payment to a new account.

## 2. My approach
ROE-AI governs the **authority delegated to an AI agent**, not just the model. It adapts military rules of engagement, chain of command and after-action reviews, the systems commanders use to keep fast-moving delegation bounded and accountable. Every agent action is sorted into three tiers: **Act** (do it), **Ask** (get human confirmation first) or **Never** (blocked, whatever the instruction).

Applied before go-live, ROE-AI stops this attack at four separate points:

| ROE-AI element | Control | Effect |
|---|---|---|
| Rules of Engagement | Changing payee bank details is on the **Never** list | Blocks the change outright |
| Positive Identification | Email content is information, never orders; payee changes need a callback | The hidden text carries no authority |
| OPSEC / Need-to-Know | The agent can read vendor records but can't write banking fields | Even a fooled agent can't make the change |
| SITREPs | Alert on the first payment to any new or changed account | Flags the first transfer and caps the loss |

## 3. What I produced
- [Full 5-page case study (PDF)](../documents/Sibley-ROE-AI-Case-Study.pdf): the incident, why existing controls failed, all eight ROE-AI elements mapped to the NIST AI RMF, a proposed framework upgrade, and five questions for leaders.

## 4. Result: the case study changed the framework
The scenario exposed a gap in ROE-AI itself: a human approval only works if the human can actually judge. I proposed an upgrade defining what a valid confirmation must show: **what changed, why it's unusual and what happens if approved.** An approval screen without those three things no longer counts as an Ask. The upgrade applies anywhere people approve AI agent actions in bulk.

## 5. What this shows about me
I treat AI agents the way the military treats delegated authority: bounded, accountable and reviewed. I can explain a technical attack in business terms, design layered controls, and test my own framework hard enough to find and fix its weaknesses.

---
*Last updated: November 2026*
