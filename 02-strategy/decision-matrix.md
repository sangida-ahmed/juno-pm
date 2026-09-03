# AI Solution Decision Matrix · Juno

## The decision

Deciding how to power Juno's anomaly detection: build a custom model, use an existing LLM API (Buy), or fine-tune an open model. Deciding now because this is a Module 1 prototype deadline, and the system prompt (Role, Rules, Output Format) is already written and tested, the only remaining question is which underlying model runs it. Waiting longer means testing the prompt logic on paper instead of against real usage data, which defeats the point of the prototype.

## Options scored

| Option | Cost | Speed | Control | Moat | Risk | Score |
|---|---|---|---|---|---|---|
| Build | 2 | 2 | 5 | 4 | 2 | 3.0 |
| Buy / API | 5 | 5 | 4 | 2 | 4 | 4.0 |
| Fine-tune | 2 | 2 | 3 | 3 | 2 | 2.4 |

## Recommendation

Buy / API. An existing LLM (like the one already powering Juno's prompt) solves this without needing training data or infrastructure. Cost and speed matter most for a V1 prototype, and the risk is low since a human still reviews every flagged anomaly before acting. Moat isn't a priority at this stage proving the workflow works is.
