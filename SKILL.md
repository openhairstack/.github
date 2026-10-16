---
name: open-hair-stack
description: Autonomous engineering, dataset validation, model training, benchmarking, and WebAssembly deployment for Open Hair Stack.
---

# Open Hair Stack — Agentic Engineering Skill

This skill defines the technical architecture, execution runbooks, dataset schemas, and automated workflows for AI agents (Claude Code, Cursor, Windsurf, Devin, Antigravity) and human engineers working on Open Hair Stack.

---

## 1. Repository Topology

The Open Hair Stack ecosystem is structured across 6 modular repositories under `github.com/openhairstack`:

```
openhairstack/
├── .github/              # Organization landing page, research library (AWESOME.md), and agent skills (SKILL.md)
├── data-pipeline/        # Public CC-BY trichoscopy datasets, annotation schema, integrity validator
├── follicle-detect/      # YOLO11/YOLOv8 training harness, Colab cloud automation, model zoo evaluation
├── scalp-analyzer-web/   # Client-side static WebAssembly/ONNX demo (live on Hugging Face Spaces)
├── scalp-analyzer/       # Python CLI and local trichoscopy analysis desktop tool
└── governance/           # Charter, Code of Conduct, Maintainer Council, 4-phase technical roadmap
```

---

## 2. Environment & Tooling Setup

### Prerequisites
* **Python:** 3.10+ (Recommended: 3.11 or 3.12)
* **Node.js:** 18+ (for WebAssembly testing and JavaScript syntax validation)
* **Package Managers:** `pip` or `uv` for Python; `npm` for Node.js
* **Git:** Commits must be signed off with Developer Certificate of Origin (`git commit -s`).

### Fast Environment Initialization
```bash
# Clone the repository you want to work on, e.g. follicle-detect:
git clone https://github.com/openhairstack/follicle-detect.git
cd follicle-detect

# Create virtual environment
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate

# Install core dependencies
pip install -r requirements.txt
pip install ultralytics onnx onnxruntime pillow numpy huggingface_hub
```

---

## 3. Core Agent Runbooks

### Runbook A: Validating a Trichoscopy Dataset (`data-pipeline`)
Run the dataset integrity validator before training or committing annotations:

```bash
cd data-pipeline
python scripts/validate_dataset.py --input datasets/follicle-v0.1/
```
**Validation Assertions Checked:**
1. Coordinates are normalized floats within `[0.0, 1.0]`.
2. Bounding boxes have positive width and height (`w > 0, h > 0`).
3. Class IDs strictly map to the standardized taxonomy:
   - `0`: `fu1` (1-hair unit)
   - `1`: `fu2` (2-hair unit)
   - `2`: `fu3` (3-hair unit)
   - `3`: `fu4` (4-hair unit)
   - `4`: `fu5` (5+-hair unit)
4. Zero split leakage between `train`, `val`, and `test` sets (checked via image SHA256 hashes).

---

### Runbook B: Model Training & Benchmarking (`follicle-detect`)
The baseline detector uses Ultralytics YOLO11n fine-tuned on standardized trichoscopy micrographs.

```bash
cd follicle-detect

# 1. Train on cloud GPU or local workstation
yolo detect train \
  data=datasets/follicle-v0.1/data.yaml \
  model=yolo11n.pt \
  epochs=60 \
  imgsz=640 \
  batch=16 \
  seed=0

# 2. Benchmark evaluation on validation split
python evaluate.py --model runs/detect/train/weights/best.pt --data datasets/follicle-v0.1/data.yaml

# 3. Export to Web-Optimized ONNX
yolo export model=runs/detect/train/weights/best.pt format=onnx imgsz=640 simplify=True
```

**v0.1 Benchmark Floor (Baseline to beat):**
- Dataset: `ranaudio/hair-follicle-detection-gjgak` (688 images, 122 validation images, 1,013 instances)
- Overall mAP50: `0.001`
- Class Recall Floor: `24.9%` on `fu2` (dominant 2-hair units)
- Precision Floor: `0.001` (v0.1 baseline, open for community scaling)

---

### Runbook C: Web Client Testing (`scalp-analyzer-web`)
The web analyzer runs 100% in the browser using `onnxruntime-web` (WebAssembly + SIMD) with zero server telemetry.

```bash
cd scalp-analyzer-web

# 1. Syntax validate JavaScript
node --check app.js

# 2. Verify all DOM element bindings
python -c "
import re
with open('index.html') as f: h = f.read()
with open('app.js') as f: j = f.read()
used = set(re.findall(r'\$\([\"\']([a-zA-Z0-9_\-]+)[\"\']\)', j))
defined = set(re.findall(r'id=[\"\']([a-zA-Z0-9_\-]+)[\"\']', h))
missing = used - defined
assert not missing, f'Missing DOM IDs: {missing}'
print('All DOM IDs verified!')
"

# 3. Serve locally for testing
python -m http.server 8000
# Open http://localhost:8000 in your browser
```

---

## 4. Open Engineering Backlog (Agent Contribution Targets)

Agents pointed at this repository should prioritize the following open tasks:

### Track 1: Computer Vision & Model Architecture
* [ ] **Issue #CV-01: Class Imbalance Loss Weighting** — Single-hair (`fu1`) and 3+-hair (`fu3-fu5`) units are under-represented. Implement Focal Loss or class-weighted cross-entropy in YOLO loss heads to improve non-fu2 recall.
* [ ] **Issue #CV-02: 3D Hair Shaft Exit Vector Regression** — Extend detection head from `[cx, cy, w, h]` to `[cx, cy, w, h, theta, phi]` (estimating azimuth and elevation angle of hair exiting the scalp).
* [ ] **Issue #CV-03: WebGPU Acceleration** — Add optional WebGPU execution provider in `scalp-analyzer-web/app.js` with fallback to WASM, enabling 60 FPS real-time live camera analysis.

### Track 2: Datasets & Scalp Diversity
* [ ] **Issue #DATA-01: Fitzpatrick Skin Tone Stratification (IV–VI)** — Ingest and curate license-clean trichoscopy images representing darker skin tones and higher melanin contrast.
* [ ] **Issue #DATA-02: Curly & Coily Hair Curvature (Types 3A–4C)** — Collect and annotate hair curl varieties where subcutaneous follicle curvature poses high transection risk.
* [ ] **Issue #DATA-03: Procedural Synthetic Scalp Generator** — Enhance `scalp-analyzer-web/make_samples.py` using procedural shaders or diffusion models to generate diverse synthetic training samples with exact ground-truth exit angles.

### Track 3: Robotics & Micro-Actuation
* [ ] **Issue #ROB-01: Micro-Robotic Kinematics Spec (5-DoF)** — Define inverse kinematics and URDF model for a 5-DoF desktop stereotaxic punch mechanism using ROS 2.
* [ ] **Issue #ROB-02: Force-Torque Dermal Boundary Detection** — Simulate load-cell signal processing algorithm detecting the dermis-to-adipose transition during punch insertion.

---

## 5. Ground Rules & Code Standards

1. **Permissive Open Licensing:**
   - All code contributions: **Apache 2.0**.
   - All datasets and documentation: **CC BY 4.0**.
   - Hardware designs: **CERN-OHL-P v2**.
2. **Absolute Patient Privacy:**
   - Never commit patient-identifiable faces, clinical records, or private hospital identifiers.
   - Any raw images must be cropped strictly to scalp dermatoscope fields with informed consent or open CC-BY provenance.
3. **Reproducibility Mandate:**
   - Every model artifact must specify: dataset SHA256, training random seed, hyperparameters, and evaluation validation metrics.
4. **Attribution:**
   - Author: Salik Shah ([@salik on X](https://x.com/salik)). Project: Open Hair Stack.
