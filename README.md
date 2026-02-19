# trace workshop: evals for PMs

## Why evals matter for PMs

As a PM, you're responsible for deciding when an AI feature is ready to ship. But "it seems good" isn't a defensible answer when leadership asks how you know.

Evals give you a structured way to answer: Are the responses meeting our brand guidelines and requirements? They turn subjective judgment into measurable criteria you can track across experiments.

This workshop walks through building evals in the Braintrust UI. If you prefer working in code, you can do everything here using the [Braintrust SDK](https://www.braintrust.dev/docs/reference/sdk).

---

## Scenario

You're a PM at Sunshine, an e-commerce company. Your support team is drowning in customer complaints about orders—refunds, shipping delays, damaged items. Historically, humans have handled these tickets, but your team wants to move to AI to scale support.

Before you ship, you need to answer: Is it good enough? Are the responses meeting our brand guidelines?

You'll run multiple experiments with different chatbot personalities:
- Concise: short, direct responses
- Polite: warm and empathetic tone
- Refund-resistant: tries to offer alternatives before approving refunds

Then you'll compare all experiments to decide which (if any) is ready to ship.

---

## Setup (in the Braintrust UI)

1. Go to [braintrust.dev](https://www.braintrust.dev) and sign in
2. Create a new project (e.g., "Sunshine Support Eval")
3. Go to Playground
4. Upload or paste in your dataset (use `dataset.csv` from this repo)
5. Paste in your system prompt
6. Choose your model
7. Run the experiment
8. Add your scorer criteria
9. Save the experiment

Repeat steps 5-9 for each personality variant you want to test.

---

## What to look for

- BrandAlignment score: Did responses follow our guidelines?
- Regressions: Did any test cases get worse between experiments?
- Individual failures: Click into low-scoring rows to see why

---

## Discussion: Would you ship this?

Look at the results and vote:
- Ship it — scores are good enough
- Needs work — some categories are failing
- Don't ship — too many regressions

---

## Files in this repo

- `dataset.csv` — 16 customer complaints across various categories. Upload this to Braintrust.
- `prompts/` — System prompts for each personality variant. Copy-paste these into the Playground.
- `scorer_criteria.txt` — The scoring rubric for BrandAlignment. Copy-paste into your scorer config.

---

## Questions?

Find Jess or Eric during the workshop!
