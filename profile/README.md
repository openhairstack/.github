<div align="center">
  <img src="https://raw.githubusercontent.com/openhairstack/.github/main/profile/logo.svg" width="120" alt="Open Hair Stack" />
  <h1>Open Hair Stack</h1>
  <p><b>Open-source tools for hair restoration research — and a free demo anyone can try in 30 seconds.</b></p>
</div>

---

### The 30-second version

Hair transplants are already performed by robots. Those machines cost $200,000+ and run on
software you can't see, can't check, and can't improve. Meanwhile the research that could
verify and improve that software sits in scattered papers with locked-down datasets.

We think the tools should be public.

So we're building them in the open: a shared dataset of carefully labeled scalp images,
detection models anyone can retrain, and a free website tool where you can upload a scalp
photo and watch the analysis happen.

No paywall. No accounts. No black boxes.

---

### Try it (no signup)

**[Scalp Analyzer demo → upload a photo, see follicular-unit detection and density stats](https://huggingface.co/spaces/openhairstack/scalp-analyzer)**

It detects the little bundles hair grows in, counts how many hairs are in each one, and
estimates density. It's a research demo, not a medical tool — [exactly what it isn't](https://github.com/openhairstack/scalp-analyzer#what-this-is-not),
in writing.

---

### What we're building

| | | |
|---|---|---|
| **Open data** | [data-pipeline](https://github.com/openhairstack/data-pipeline) — every openly-licensed follicle dataset in one place, plus tools that catch broken annotations. The goal: the biggest freely-redistributable scalp dataset in the world. | labelers welcome, no code needed |
| **Open models** | [follicle-detect](https://github.com/openhairstack/follicle-detect) — train a hair-follicle detector in one click on free cloud compute. Every model we publish comes with its scores, including the mediocre ones. | CV/ML contributors |
| **Open demo** | [scalp-analyzer](https://github.com/openhairstack/scalp-analyzer) — the public website tool. Every number it prints is a function you can read in the code. | try it, break it, file issues |
| **Open rules** | [governance](https://github.com/openhairstack/governance) — how the project is run, who decides what, and what it will never do (see the Charter). | read the one-page Charter |

**Just curious?** [Start with the glossary](https://github.com/openhairstack/governance/blob/main/GLOSSARY.md) — "follicle unit", "graft", "mAP", in plain English. We wrote it for journalists and family members.

---

### Why open source here

- **The bottleneck is labeled data.** One lab can label 700 images. Fifty labs and students
  can label 35,000. That's the whole math of why this shouldn't be a private effort.
- **Everyone should be able to check the answers.** Right now, follicle detection claims
  across this field can't even be compared to each other — different datasets, different
  formats, no shared benchmark. Publishing our mediocre v0.1 with its scores gives the field
  a floor to stand on.
- **It should be usable where the machines aren't.** Most clinics in the world will never
  see a $200k robot. Open verification tools run on a laptop.

---

### Our ground rules (short version)

1. **Everything is open.** Code: Apache 2.0. Data: CC BY 4.0.
2. **No patient data. Ever.** Photos of identifiable people never enter our datasets. [Charter](https://github.com/openhairstack/governance/blob/main/CHARTER.md).
3. **Not a medical device.** Nothing here diagnoses or treats anyone. We say so everywhere.
4. **We publish our failures.** v0.1 scores are mediocre *on purpose* — a public floor beats a secret ceiling.
5. **The roadmap includes kill criteria.** If people don't use it, we sunset it gracefully and archive it.

<br/>

<div align="center">
  <b>Questions, press, or just curious?</b> DM <a href="https://x.com/salik">@salik on X</a> ·
  <a href="https://github.com/orgs/openhairstack/discussions">GitHub Discussions</a><br/>
  <sub>Built by people who think the machines moving your hair around shouldn't be black boxes.</sub>
</div>
