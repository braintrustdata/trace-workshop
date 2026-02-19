# TRACE Workshop: Evals for PMs

Run your first AI evaluation in 15 minutes.

## Scenario

You're a PM at **Sunshine Co.**, an e-commerce company. Your team just built an AI chatbot to handle customer support. Before you ship it, you need to answer: **Is it good enough?**

You'll run two experiments:
1. **Baseline:** GPT-4o with no guidance
2. **Improved:** GPT-4o with brand-aligned instructions

Then you'll compare them and decide: **Would you ship this?**

---

## Setup (3 min)

### 1. Clone this repo
```bash
git clone https://github.com/braintrustdata/trace-workshop.git
cd trace-workshop
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Set your API key
```bash
export BRAINTRUST_API_KEY="your-api-key-here"
```

> **Note:** We'll provide API keys during the workshop.

---

## Run the Experiments (10 min)

### Step 1: Run the baseline (no system prompt)
```bash
python eval_baseline.py
```

This runs GPT-4o with no instructions on 16 customer complaints.

### Step 2: Run the improved version (brand-aligned)
```bash
python eval_improved.py
```

This runs the same test cases with a brand-aligned system prompt.

### Step 3: Compare in Braintrust

1. Go to [braintrust.dev](https://www.braintrust.dev)
2. Open the **TRACE_Workshop** project
3. Click **Experiments**
4. Select both experiments to compare side-by-side

---

## What to Look For

- **BrandAlignment score:** Did responses follow our guidelines?
- **Regressions:** Did any test cases get worse?
- **Individual failures:** Click into low-scoring rows to see why

---

## Discussion: Would You Ship This?

Look at the results and vote:
- ✅ **Ship it** — scores are good enough
- ⚠️ **Needs work** — some categories are failing
- ❌ **Don't ship** — too many regressions

---

## Files in This Repo

| File | Purpose |
|------|---------|
| `dataset.py` | 16 customer complaints (various categories) |
| `scorer.py` | BrandAlignment LLM-as-judge scorer |
| `eval_baseline.py` | Experiment 1: No system prompt |
| `eval_improved.py` | Experiment 2: Brand-aligned prompt |

---

## Questions?

Find Jess or Eric during the workshop!
