# Open Hair Stack

**The open-source stack for AI-assisted hair restoration.**

Hair transplant robots exist. ARTAS and HAIRO cost $200k+ and run closed software. The research on follicle detection exists but is scattered across papers, dead repos, and inconsistently licensed datasets. Nobody has built the shared, open, benchmarked layer between them.

Open Hair Stack is that layer:

| Component | What it is | Repo |
|---|---|---|
| **Data** | Consolidated, license-clean follicle datasets + conversion tooling + community labeling pipeline | `data-pipeline` |
| **Models** | Fine-tuning and benchmark harness for follicle detection (YOLO-OBB), with published weights + reproducible evals | `follicle-detect` |
| **Demo** | Free, runnable scalp analyzer: detection, density stats, Norwood heuristic, graft-planning simulation | `scalp-analyzer` |
| **Governance** | Charter, decision process, contributor ladder | `governance` |

### Status: v0.1 pre-launch

- Model baseline in training on a free GPU (Colab notebook, one click)
- First public Space and model weights: this week
- Looking for: computer vision engineers, roboticists, annotators, dermatology advisors

### What this is not

A medical device. A diagnostic tool. A cure. It is research software for the hair restoration research community, and an educational demo. Full disclaimer: see `scalp-analyzer/MEDICAL_DISCLAIMER.md`.

### Get started in 60 seconds

1. Try the demo: [HF Space](https://huggingface.co/spaces/openhairstack/scalp-analyzer)
2. Run training yourself: [`follicle-detect/notebooks/train_colab.ipynb`](https://github.com/openhairstack/follicle-detect)
3. Join the Discord: [invite link]
4. Pick a bounty: [bounties board]

### Licensing

Code: Apache 2.0 · Docs & data: CC BY 4.0 · Hardware (when it lands): CERN-OHL. One rule: everything you contribute stays open.
