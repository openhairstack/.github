<div align="center">
  <img src="https://raw.githubusercontent.com/openhairstack/.github/main/profile/logo.svg" width="130" alt="Open Hair Stack Emblem" />
  <h1>Open Hair Stack</h1>
  <p><b>Open-source computer vision, standardized datasets, and stereotaxic robotics for autonomous hair restoration and bio-implantation.</b></p>

  <p>
    <a href="https://huggingface.co/spaces/openhairstack/scalp-analyzer"><img src="https://img.shields.io/badge/Live%20Demo-HuggingFace%20Space-blue?style=flat-square" alt="Live Demo" /></a>
    <a href="https://huggingface.co/openhairstack/follicle-fu-v0.1"><img src="https://img.shields.io/badge/Model%20Zoo-follicle--fu--v0.1-orange?style=flat-square" alt="Model Zoo" /></a>
    <a href="https://github.com/openhairstack/governance/blob/main/COMMONS-AND-INVESTMENT.md"><img src="https://img.shields.io/badge/Sponsor%20%26%20Invest-Commons%20Blueprint-yellow?style=flat-square" alt="Sponsor & Invest" /></a>
    <a href="https://github.com/openhairstack/.github/blob/main/AWESOME.md"><img src="https://img.shields.io/badge/Research%20Library-Awesome%20List-purple?style=flat-square" alt="Awesome Research Library" /></a>
    <a href="https://github.com/openhairstack/.github/blob/main/SKILL.md"><img src="https://img.shields.io/badge/Agent%20Ready-SKILL.md-success?style=flat-square" alt="Agent Ready Skill" /></a>
    <a href="https://github.com/openhairstack/governance/blob/main/CHARTER.md"><img src="https://img.shields.io/badge/License-Apache%202.0%20%7C%20CC%20BY%204.0-green?style=flat-square" alt="License" /></a>
    <a href="https://x.com/salik"><img src="https://img.shields.io/badge/Contact-@salik%20on%20X-black?style=flat-square&logo=x" alt="Contact on X" /></a>
  </p>
</div>

> [!TIP]
> **Strategic Collaboration, Research & Sponsor Inquiries:** We are partnering with clinical trichologists, physical AI roboticists, and strategic capital to accelerate the public biomedical frontier. Review our [Commons, Governance & Investment Blueprint](https://github.com/openhairstack/governance/blob/main/COMMONS-AND-INVESTMENT.md) or submit a proposal via the [Intake Form](https://tally.so/r/3yPJEk). Direct inquiries: [@salik on X](https://x.com/salik).

---

### The Executive Summary

Hair restoration and follicular unit extraction (FUE) are increasingly driven by robotic systems. Today, commercial surgical robots (such as ARTAS and HAIRO) cost upwards of $200,000 and run on closed, proprietary software that independent researchers, clinicians, and patients cannot inspect, audit, or build upon.

Meanwhile, academic papers on follicle detection (like YOLO-OHFD and Hair-YOLO) remain fragmented across paywalled journals with private, unreleased datasets.

**Open Hair Stack** is the first license-clean, open-source initiative creating a transparent scientific commons:
1. **Clean Data Commons:** Standardized, openly licensed trichoscopy datasets under CC BY 4.0.
2. **Reproducible Vision Harness:** Lightweight, accessible neural detection models trained on open compute.
3. **100% Client-Side WebAssembly Demo:** A private browser application where anyone can run follicle segmentation locally with zero server uploads.
4. **Autonomous Robotics Roadmap:** A concrete, 4-phase trajectory toward sub-millimeter stereotaxic robotic actuation and automated implantation of bio-engineered hair organoids.

---

### 🎯 The North Star Vision

> **Our Ultimate Ambition:** To build an open, accessible, sub-millimeter robotic platform capable of autonomous hair follicle harvesting, 3D trajectory planning, and high-density implantation of autologous grafts and bio-cloned follicle organoids with neural-chip level micro-precision.

In the near term, we automate tedious, error-prone manual follicular unit counting and density mapping. In the long term, as regenerative medicine pioneers (such as the Tsuji Lab at RIKEN, Stemson Therapeutics, and dNovo) succeed in multiplying millions of cloned hair follicle primordia in-vitro, manual surgical implantation will become humanly impossible due to sheer volume and micro-scale fragility. 

Open Hair Stack is architecting the open computational and robotic actuation foundation to make high-density bio-implantation a reality.

---

### 🔬 Try the Live Demo (100% Private, Zero Server Uploads)

👉 **[Launch the Scalp Analyzer Demo on Hugging Face Spaces](https://huggingface.co/spaces/openhairstack/scalp-analyzer)**

* **Client-Side Neural Inference:** The YOLO11n detection model executes directly in your web browser via `onnxruntime-web` WebAssembly (WASM) + SIMD. **No photos or patient pixels ever leave your device.**
* **Dynamic Reticle Preview:** Displays uploaded photo thumbnails with optical alignment markers and image metadata.
* **Follicular-Unit Classification:** Classifies bundles into standardized clinical classes (`fu1` to `fu5`) and calculates mean hairs per graft.
* **Interactive Class Filtering:** Isolate single-hair, 2-hair, or multi-hair clusters on the canvas in real-time.
* **Graft Planning Sandbox & Export:** Explores illustrative zone-allocation heuristics and exports auditable, timestamped JSON research reports.

---

### 📦 Current Status & What Has Been Built (v0.1 Milestone)

```
openhairstack/
├── 📂 data-pipeline/        # Automated dataset validation harness, coordinate normalizer, class schema
├── 👁️ follicle-detect/      # Ultralytics YOLO11n fine-tuning pipeline & Colab cloud automation
├── 🔬 scalp-analyzer-web/   # Client-side static WebAssembly/ONNX application (Hugging Face Space)
├── 💻 scalp-analyzer/       # Python CLI and desktop trichoscopy analysis toolkit
├── ⚖️ governance/           # Charter, Code of Conduct, Maintainer Council, 4-Phase Technical Roadmap
└── 📚 .github/              # Organization profile, Awesome Research Library, Agent Skill file
```

1. **Dataset Integrity Harness ([`data-pipeline`](https://github.com/openhairstack/data-pipeline)):**
   - Implemented an automated validation suite verifying coordinate normalization `[0.0, 1.0]`, positive box areas, and strict zero-leakage splits across train/val/test splits via image SHA256 checksums.
   - Standardized the 5-class follicular unit taxonomy: `fu1` (1-hair), `fu2` (2-hair), `fu3` (3-hair), `fu4` (4-hair), and `fu5` (5+-hair).
2. **Model Training & Model Zoo ([`follicle-detect`](https://github.com/openhairstack/follicle-detect)):**
   - Fine-tuned Ultralytics YOLO11n for 60 epochs on cloud GPU compute.
   - Published verified model weights on Hugging Face: [`openhairstack/follicle-fu-v0.1`](https://huggingface.co/openhairstack/follicle-fu-v0.1) (`model.onnx`, 10.6 MB, float32).
3. **Private In-Browser Analyzer ([`scalp-analyzer-web`](https://github.com/openhairstack/scalp-analyzer-web)):**
   - Single-threaded WASM + SIMD execution with instant 60 FPS slider filtering via cached tensor decoding.
   - Full suite of KPI stat cards, zone miniaturization gradient analysis, and direct PNG / JSON report export.

---

### 📊 Honest Metrics & Current Limitations

We operate on radical transparency: **an honest public baseline beats an unverifiable marketing claim.**

* **The Baseline Floor (v0.1):**
  - Validation Split: 122 trichoscopy images, 1,013 ground-truth instances.
  - Overall mAP50: `0.001` · Overall Recall: `0.050`.
  - **Dominant Class Recall: 24.9% on `fu2` (2-hair follicular units).**
* **Known Technical Limitations:**
  1. **Dataset Scale & Source Homogeneity:** v0.1 was trained on 688 images from a single source (`ranaudio/hair-follicle-detection-gjgak`). It lacks diversity across lighting conditions, dermatoscope optics, and scalp pathologies.
  2. **Demographic & Texture Gaps:** Fitzpatrick skin phototypes IV–VI and curly/coily hair curl patterns (3A–4C) are heavily under-represented.
  3. **2D Surface vs. 3D Subsurface Trajectory:** Current detection locates the surface exit pore (ostium), but hair follicles curve subcutaneously into the dermis at acute angles (30°–60°). Physical robotic harvesting requires 3D exit vector estimation to prevent transection.
  4. **Class Imbalance:** Due to natural biological predominance, 2-hair units dominate the training set, causing lower recall on single-hair (`fu1`) and 3+-hair (`fu3–fu5`) bundles.

---

### 🗺️ The Strategic 4-Phase Roadmap

Detailed technological specifications and milestone breakdowns are documented in [**`governance/ROADMAP.md`**](https://github.com/openhairstack/governance/blob/main/ROADMAP.md).

```
Phase 1: Foundation CV & Data Commons (Current — 2026 Q4)
  └─ Ingest 5,000+ diverse CC-BY images · Fitzpatrick I–VI · Focal loss for class rebalancing · WebGPU engine

Phase 2: Stereotaxic Depth Sensing & Micro-Planning (2027)
  └─ Dual-camera stereoscopic micro-calipers · 3D exit vector regression [x, y, z, roll, pitch, yaw] · OCT depth mapping · Safe Donor Area (SDA) contouring

Phase 3: Open Hardware & Micro-Actuation Rig (2027–2028)
  └─ 5/6-DoF micro-manipulator Kinematics (CERN-OHL-P) · Sub-mm oscillating punch (0.8mm) · Force-torque dermal transition sensing · ROS 2 real-time control

Phase 4: Autonomous Implantation & Bio-Cloning Integration (North Star)
  └─ Automated micro-graft sorting & implantation cartridges (30–45 FU/cm²) · Bio-docking for in-vitro cultured follicle organoids · Sub-100µm stereotaxy
```

---

### 🤝 Why We Urgently Need More Data & How to Contribute

This project is collaborative by construction. **We cannot build neural-chip level precision robotics without open scientific data.**

#### 1. Donate & Annotate Data (No Code Needed!)
If you are a dermatologist, trichologist, clinic, or researcher with access to scalp dermatoscope imagery:
* We urgently need **de-identified, non-patient-identifiable** trichoscopy crops representing:
  - **Fitzpatrick Skin Types IV, V, and VI** (darker scalp skin tones, higher melanin contrast).
  - **Curly and Coily Hair Textures (3A, 3B, 3C, 4A, 4B, 4C)** where subcutaneous follicle curvature is pronounced.
  - **Diverse Scalp Conditions:** Androgenetic alopecia (AGA), alopecia areata, cicatricial alopecias, and healthy controls.
* Review our [`data-pipeline/ANNOTATION_GUIDE.md`](https://github.com/openhairstack/data-pipeline/blob/main/ANNOTATION_GUIDE.md) and submit datasets via pull request.

#### 2. Computer Vision & Machine Learning Engineers
* Implement class-imbalance loss functions (Focal Loss, Dice Loss) to boost recall on `fu1` and `fu3–fu5`.
* Help build 3D hair shaft exit vector regression heads (`[cx, cy, w, h, roll, pitch, yaw]`).
* Implement WebGPU execution in `scalp-analyzer-web/app.js` for 60 FPS live camera tracking.

#### 3. Robotics & Hardware Engineers
* Help model inverse kinematics and URDF files for 5-DoF/6-DoF Cartesian and delta micro-manipulators.
* Design piezoelectric force-torque sensing algorithms to detect dermal-to-adipose layer transitions.
* Contribute deterministic C++20 ROS 2 nodes for visual servoing and motion compensation.

---

### 🤖 Point Your AI Agent Here: Machine-Readable Skill Spec

Open Hair Stack is architected for seamless pair-programming with autonomous AI agents (Claude Code, Cursor, Windsurf, Devin, Antigravity).

Point your agent directly at our standardized skill specification:
👉 **[`.github/SKILL.md`](https://github.com/openhairstack/.github/blob/main/SKILL.md)**

The skill file provides machine-executable runbooks for:
```bash
# Validate any dataset against the integrity schema:
python data-pipeline/scripts/validate_dataset.py --input <path>

# Run model training and benchmark evaluations:
python follicle-detect/train.py --data follicle-v0.1 --model yolo11n.pt
python follicle-detect/evaluate.py --model best.pt --data follicle-v0.1

# Syntax and DOM verification for web applications:
node --check scalp-analyzer-web/app.js
```

---

### 📚 Research Library & Prior Art

We maintain an exhaustive, curated bibliography of academic papers, commercial robotic platforms, OCT subsurface imaging studies, and regenerative hair cloning breakthroughs in:
👉 [**Awesome Computational Trichology & Hair Robotics (`AWESOME.md`)**](https://github.com/openhairstack/.github/blob/main/AWESOME.md)

**Key Credits & Scientific Lineage:**
* **Commercial Systems:** ARTAS Robotic Hair Restoration (Restoration Robotics / Venus Concept), HAIRO Robotic System (China NMPA Class III cleared, 2025).
* **Computer Vision Papers:** Hair-YOLO (2025), YOLO-OHFD (2025), Fudan Huashan Trichoscopy Dataset, ICANN 2023 Follicular Classification.
* **Regenerative Medicine:** Tsuji Lab / RIKEN (de-novo hair follicle germ organogenesis), Stemson Therapeutics, dNovo, Organ Technologies.

---

### ⚖️ Governance, Ethics & Disclaimers

* **Permissive Licensing:** All software code is released under **Apache 2.0**; all datasets, benchmarks, and documentation under **CC BY 4.0**; open hardware designs under **CERN-OHL-P v2**.
* **Zero Patient Liability:** Datasets strictly exclude patient-identifiable imagery, faces, and medical record numbers.
* **Research Software Notice:** Open Hair Stack is experimental research and educational software. It does not provide medical diagnoses, treatment planning, or clinical advice.

---

<div align="center">
  <h3>Questions, Collaborations, or Research Sponsorship?</h3>
  <p>A project by Salik Shah. Connect for technical discussions, research partnerships, or opportunities:</p>
  <p>
    💬 <b>Contact on X:</b> <a href="https://x.com/salik"><b>@salik</b></a> &nbsp;·&nbsp;
    💬 <b>GitHub Discussions:</b> <a href="https://github.com/orgs/openhairstack/discussions">Join the Community</a> &nbsp;·&nbsp;
    🌐 <b>Org:</b> <a href="https://github.com/openhairstack">openhairstack</a>
  </p>
  <br/>
  <sub><i>Open Hair Stack — Open science, computer vision, and stereotaxic robotics for the future of hair restoration.</i></sub>
</div>
