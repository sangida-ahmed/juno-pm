# AI Strategy One-Pager - Juno Automated Prioritization

## 1. Problem & Workflow

The Problem: Right now, if Messages usage drops on a given day, there's no way to tell a real problem from a normal quiet day. A Thursday with almost no usage looks the same on a spreadsheet as a normal slow Saturday, just a number below average. Nobody notices until someone happens to scroll through their usage history days later, by which point the "why" is impossible to trace.

Prevention: Juno explicitly prevents a real usage problem from going unnoticed because it blends into normal weekly noise.

## 2. Target Metrics

Cycle time: Time to catch a real anomaly, from ~7 days (manual weekly review) down to under 24 hours.

Leadership proof: False positive rate stays under 10%, meaning Juno rarely cries wolf on a normal dip, so people actually trust its flags instead of tuning them out.

## 3. Autonomy Level

Choice: Copilot. Juno flags what looks unusual and explains why, but a person always decides what to actually do about it.

Explicitly avoiding: Agent. We're not letting Juno automatically escalate, notify a team, or take any action on its own. The cost of a wrong call (missing a real issue, or raising a false alarm) is still too high to hand off the final decision.

## 4. Data & Model Approach

Approach: Buy (LLM). An existing AI model, given clear rules to follow, can already read a small table of usage numbers and tell a real drop from a normal one. No custom infrastructure needed.

Explicitly avoiding: Refine (Fine-tune). There's no dataset of labeled "real problem" vs. "normal dip" examples to train on, and this is a rules-following problem, not a style or tone problem, so fine-tuning wouldn't actually improve anything.

## 5. Risks & Mitigations

Risk: Juno could start treating every dip as urgent, so people stop trusting its flags and ignore them entirely, the same way people ignore a car alarm that goes off too often.

Mitigation: Every flagged day requires a calculated baseline first, and normal patterns (like weekends) are explicitly excluded from being flagged, so only real deviations get raised.

## 6. V1 Scope

In: Reading daily Messages usage data (minutes, opens) and flagging days that look meaningfully unusual, with a severity rating and a reason.

Out: Juno does not access any app besides Messages. Juno does not take any automatic action (no notifications sent, no tickets created) it only drafts a flagged report for a human to review.
