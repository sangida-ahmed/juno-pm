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

Buy / API is the right choice. The task is simple: read a small table of Messages usage numbers and figure out which day looks unusual. That doesn't require building or retraining a new model from scratch, since an existing model (like the one already running behind Juno in our prototype) can already do it well when given clear rules to follow. We already proved this works: when we tested Juno's system prompt, it correctly caught a real drop on a Thursday while correctly ignoring a normal dip over the weekend. Since the goal right now is proving the idea works, not building something no one else can copy, using an existing model to power Juno is the smartest and fastest option.
