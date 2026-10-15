<div align="center">
  <img src="https://raw.githubusercontent.com/openhairstack/.github/main/profile/logo.svg" width="130" alt="Open Hair Stack Logo" />
  <h1>Open Hair Stack</h1>
  <p><b>Open-source computer vision tools for hair restoration research — with a private, zero-install browser demo anyone can try.</b></p>

  <p>
    <a href="https://huggingface.co/spaces/openhairstack/scalp-analyzer"><img src="https://img.shields.io/badge/Live%20Demo-HuggingFace%20Space-blue?style=flat-square" alt="Live Demo" /></a>
    <a href="https://github.com/openhairstack/governance/blob/main/CHARTER.md"><img src="https://img.shields.io/badge/License-Apache%202.0%20%7C%20CC%20BY%204.0-green?style=flat-square" alt="License" /></a>
    <a href="https://x.com/salik"><img src="https://img.shields.io/badge/Founder-@salik%20on%20X-black?style=flat-square&logo=x" alt="X / Twitter" /></a>
  </p>
</div>

---

### The 30-Second Summary

Hair restoration and follicular unit extraction (FUE) are increasingly powered by robotic systems. Today, those systems cost upwards of $200,000 and run on closed, proprietary software that independent researchers, clinicians, and patients cannot inspect, audit, or build upon.

Meanwhile, academic research on follicle detection remains scattered across papers with private, unreleased datasets.

**We believe the scientific foundation of hair health should be open to everyone.**

**Open Hair Stack** is building a transparent, community-driven ecosystem:
- **Clean Data:** Publicly licensed, carefully annotated trichoscopy datasets.
- **Reproducible Vision Models:** Lightweight detection models anyone can train on free cloud compute.
- **Client-Side Browser Demo:** A private web tool where you can test follicle detection directly on your device with zero server uploads.

No paywalls. No mandatory accounts. No closed black boxes.

---

### Try the Demo (Free & 100% Private)

👉 **[Launch the Scalp Analyzer Demo](https://huggingface.co/spaces/openhairstack/scalp-analyzer)**

* **Client-Side AI:** The detection model (YOLO11n via ONNX Runtime Web) runs directly in your web browser. Your photos are **never uploaded to any server or cloud database**, ensuring complete privacy.
* **Follicular-Unit Analysis:** Automatically counts hair bundles (`fu1` to `fu5`) and estimates local follicular density.
* **Educational & Research Purpose:** Built strictly for research exploration and benchmarking, not clinical medical diagnosis.

---

### The Core Repositories

| Repository | What It Provides | How to Get Involved |
|---|---|---|
| 📂 **[data-pipeline](https://github.com/openhairstack/data-pipeline)** | Clean CC-BY trichoscopy datasets, automatic re-labelers, and annotation validation tools. | Labelers & trichology enthusiasts welcome — no code needed. |
| 👁️ **[follicle-detect](https://github.com/openhairstack/follicle-detect)** | YOLO11 training pipeline with a one-click Google Colab notebook and published baseline weights. | ML engineers & computer vision researchers. |
| 🔬 **[scalp-analyzer-web](https://github.com/openhairstack/scalp-analyzer-web)** | Client-side web demo powered by WebAssembly. Zero hosting cost, private by design. | Web developers & UI/UX contributors. |
| ⚖️ **[governance](https://github.com/openhairstack/governance)** | Our project charter, ethics policies, contributor guidelines, and plain-English glossary. | Review our [Charter](https://github.com/openhairstack/governance/blob/main/CHARTER.md) and join discussions. |

> 💡 **New to the terminology?** Read our **[Plain-English Glossary](https://github.com/openhairstack/governance/blob/main/GLOSSARY.md)** explaining terms like *follicular unit*, *donor density*, and *mAP* in simple language.

---

### Why Open Source?

1. **Collaborative Data Scaling:** A single lab can annotate a few hundred images. A distributed open community of researchers, clinics, and contributors can curate tens of thousands of diverse trichoscopy cases across all hair textures and scalp conditions.
2. **Transparent Benchmarking:** Current literature lacks standardized public benchmarks. Publishing our v0.1 baseline scores unvarnished establishes an honest, reproducible benchmark floor for the entire field.
3. **Global Accessibility:** Specialized clinics in major medical centers may afford robotic systems, but independent researchers, students, and clinics worldwide deserve access to open verification tools.

---

### Ground Rules & Values

* **Open Licenses:** Code is licensed under **Apache 2.0**; datasets and documentation under **CC BY 4.0**.
* **Zero Patient Data Liability:** Only non-identifiable, license-clean trichoscopic images enter our datasets.
* **Not a Medical Device:** Open Hair Stack is research and educational software. It does not provide medical advice, diagnosis, or surgical planning.
* **Transparent Metrics:** We publish all evaluation numbers openly. A transparent public baseline beats an unverifiable claim.

---

<div align="center">
  <h3>Questions, Press, or Community Support?</h3>
  <p>Connect directly with founder Salik Shah for questions, collaborations, or support:</p>
  <p>
    💬 <b>DM on X:</b> <a href="https://x.com/salik"><b>@salik</b></a> &nbsp;·&nbsp;
    💬 <b>GitHub:</b> <a href="https://github.com/orgs/openhairstack/discussions">Discussions</a> &nbsp;·&nbsp;
    🌐 <b>Org:</b> <a href="https://github.com/openhairstack">openhairstack</a>
  </p>
  <br/>
  <sub><i>Open Hair Stack — Open science and computer vision for hair restoration research.</i></sub>
</div>
