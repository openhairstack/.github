# Awesome Computational Trichology & Hair Robotics

> A curated research library of papers, datasets, commercial systems, robotics architectures, and regenerative medicine projects dedicated to open computer vision, robotic follicular extraction, and automated hair restoration.

[![Open Hair Stack](https://img.shields.io/badge/Open%20Hair%20Stack-Research%20Commons-blue?style=flat-square)](https://github.com/openhairstack)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-green.svg?style=flat-square)](https://creativecommons.org/licenses/by/4.0/)

---

## Contents
1. [Commercial Robotic Systems](#1-commercial-robotic-systems)
2. [Computer Vision & Follicle Detection Papers](#2-computer-vision--follicle-detection-papers)
3. [Dermatoscopy & Trichoscopy Datasets](#3-dermatoscopy--trichoscopy-datasets)
4. [Subsurface Imaging & Optical Coherence Tomography (OCT)](#4-subsurface-imaging--optical-coherence-tomography-oct)
5. [Robotic Micro-Actuation & Surgical Kinematics](#5-robotic-micro-actuation--surgical-kinematics)
6. [Hair Cloning, Follicle Organoids & Regenerative Medicine](#6-hair-cloning-follicle-organoids--regenerative-medicine)
7. [Clinical Standards, Graft Survival & Safe Donor Area](#7-clinical-standards-graft-survival--safe-donor-area)
8. [Open Source Tools & Frameworks](#8-open-source-tools--frameworks)

---

## 1. Commercial Robotic Systems

* **ARTAS Robotic System (Restoration Robotics / Venus Concept)**
  * *Overview:* First FDA-cleared commercial robotic FUE system (510(k) cleared in 2011). Utilizes multi-camera stereoscopic vision mounted on an industrial KUKA or proprietary robotic arm.
  * *Vision & Mechanism:* Dual-puncture system (sharp inner punch followed by blunt rotating outer punch) tracking exit angle and depth to minimize graft transection.
  * *Status:* Deployed globally, proprietary closed-source vision algorithms and motion control.
* **HAIRO Robotic System (China)**
  * *Overview:* Received China NMPA Class III medical device clearance in 2025 for autonomous follicular unit extraction.
  * *Vision & Mechanism:* Real-time deep learning follicle segmentation combined with high-speed stereoscopic visual servoing.
  * *Status:* Commercial in select hospitals; proprietary hardware and closed model weights.
* **NeoGraft & SmartGraft (Automated/Pneumatic Systems)**
  * *Overview:* Hand-held semi-automated pneumatic extraction and suction tools.
  * *Status:* Clinical standard for manual FUE assistance, lack autonomous vision-guided robotic actuation.

---

## 2. Computer Vision & Follicle Detection Papers

* **Hair-YOLO: Real-Time Hair Follicle Detection and Counting in Trichoscopic Images** (2025)
  * *Key Contribution:* Lightweight YOLO architecture with custom attention heads optimized for dense follicle pore detection in high-resolution trichoscopy micrographs.
  * *Limitation:* Trained on private hospital datasets; weights and raw annotations not publicly released.
* **YOLO-OHFD: An Optical Hair Follicle Detector for Dermatoscope Analysis** (2025)
  * *Key Contribution:* Multi-scale feature fusion for detecting miniaturized single hairs vs terminal multi-hair clusters in androgenetic alopecia.
  * *Relevance:* Demonstrates that anchor-free detectors improve localization in crowded scalp crops.
* **Automated Follicular Unit Classification Using Deep Convolutional Networks** (*ICANN 2023*)
  * *Key Contribution:* Categorizing follicular units into 1-hair (`fu1`), 2-hair (`fu2`), and 3+-hair bundles to compute mean hair-to-graft ratio.
* **Dermatoscopic Micro-Vessel and Follicular Feature Segmentation via U-Net Variations** (*IEEE TBME, 2022*)
  * *Key Contribution:* Segmenting peri-follicular erythema, white dots, and micro-vascular loops indicative of cicatricial alopecias.
* **3D Hair Shaft Exit Angle and Trajectory Estimation from Single-View Polarized Trichoscopy** (*CVPR Workshop on Medical CV, 2024*)
  * *Key Contribution:* Using directional shading and cross-polarized light reflections to regress subcutaneous follicle orientation vector `(dx, dy, dz)`.

---

## 3. Dermatoscopy & Trichoscopy Datasets

* **`ranaudio/hair-follicle-detection-gjgak` (Roboflow Universe, 2025)**
  * *Size:* 688 trichoscopy micrographs with 5-class follicular unit bounding boxes (`fu1`–`fu5`).
  * *License:* CC BY 4.0.
  * *Note:* Forms the open baseline dataset for Open Hair Stack v0.1.
* **Fudan Huashan Trichoscopy Dataset (China)**
  * *Scope:* Large clinical repository of scalp dermatoscope images across diverse alopecia conditions.
  * *Status:* Academic research access only; restricted commercial redistribution.
* **HAM10000 & BCN20000 (ISIC Archive)**
  * *Relevance:* While focused on pigmented skin lesions, contains thousands of high-resolution scalp and hair-bearing skin dermatoscope images with rich Fitzpatrick skin type diversity.
  * *License:* CC BY-NC / CC BY.

---

## 4. Subsurface Imaging & Optical Coherence Tomography (OCT)

* **High-Definition Optical Coherence Tomography (HD-OCT) for In-Vivo Hair Follicle Visualization** (*Journal of Biophotonics, 2021*)
  * *Core Finding:* Optical coherence tomography provides depth resolution up to 1.5–2.0 mm, enabling direct measurement of follicle bulb depth and subcutaneous curvature without histology.
* **High-Frequency Ultrasound (HFUS, 50–70 MHz) in Trichology** (*Skin Research and Technology, 2023*)
  * *Core Finding:* Non-invasive differentiation between terminal follicles (depth > 3mm) and vellus/miniaturized follicles (depth < 1.5mm) in androgenetic alopecia.
* **Polarized Cross-Polarization Microscopy for Dermal Matrix and Follicular Boundary Definition** (*Biomedical Optics Express, 2022*)
  * *Core Finding:* Eliminates surface stratum corneum glare, revealing true epidermal ostium and infundibulum borders.

---

## 5. Robotic Micro-Actuation & Surgical Kinematics

* **Sub-Millimeter Needle and Punch Insertion Kinematics** (*IEEE Transactions on Robotics, 2020*)
  * *Core Finding:* Oscillatory / rotational punch actuation at 2,000–5,000 RPM significantly reduces skin depression and tissue distortion compared to axial blunt puncture, decreasing follicle transection rates below 3%.
* **Force-Torque Sensing for Real-Time Dermal Layer Transition Detection** (*Robotics and Autonomous Systems, 2022*)
  * *Core Finding:* Micro-load cells behind the extraction punch detect the distinctive force drop when crossing from dense dermis into subcutaneous adipose tissue, triggering instant punch retraction.
* **Visual Servoing for Physiological Motion Compensation in Scalp Surgery** (*Int. Journal of Computer Assisted Radiology and Surgery, 2023*)
  * *Core Finding:* 60 Hz optical tracking compensating for patient respiration, pulse, and micro-movements within a 0.05 mm envelope.

---

## 6. Hair Cloning, Follicle Organoids & Regenerative Medicine

* **De Novo Morphogenesis of Hair Follicle Germs from Cultured Epithelial and Mesenchymal Cells** (*Nature Communications / Tsuji Lab, RIKEN, 2018*)
  * *Breakthrough:* Reconstituting human dermal papilla cells and epithelial stem cells into bio-engineered follicular units that cycle and grow hair shafts when transplanted into mice.
* **Stemson Therapeutics & dNovo (Induced Pluripotent Stem Cells to Follicles)**
  * *Overview:* Differentiation of human iPSCs into autologous dermal papilla and epithelial stem cells to generate inexhaustible follicle seed banks.
  * *Engineering Bottleneck:* Once millions of cloned follicle organoids are grown in-vitro, manual surgical implantation is humanly impossible due to volume. Autonomous, micro-precision robotic implantation becomes a biological necessity.
* **Organ Technologies (Japan)**
  * *Overview:* High-throughput automated 3D bio-fabrication of hair follicle primordia.
* **Epibiotech (Korea)**
  * *Overview:* Dermal papilla cell spheroid culture and cell-based therapeutic micro-injection platforms.

---

## 7. Clinical Standards, Graft Survival & Safe Donor Area

* **The Safe Donor Area (SDA) in Hair Transplantation** (*Unger et al., Dermatologic Surgery*)
  * *Clinical Standard:* Delineating the parietal and occipital scalp regions resistant to dihydrotestosterone (DHT) binding for lifelong graft permanence.
* **Follicular Density Benchmarks across Global Ethnicities** (*ISHRS Practice Guidelines*)
  * *Standard:* Normal scalp averages 65–100 FU/cm² (150–220 hairs/cm²). Natural aesthetic restoration targets 25–45 FU/cm² in recipient zones depending on hair caliber and contrast.
* **Graft Hydration, Temperature, and Ischemia Time in FUE Viability** (*Hair Transplant Forum International*)
  * *Standard:* For every hour grafts remain out of body at room temperature, survival decreases by ~1–2%. Real-time closed-loop robotic extraction-and-immediate-implantation maximizes viability.

---

## 8. Open Source Tools & Frameworks

* **[Open Hair Stack (`openhairstack`)](https://github.com/openhairstack)** — Open computer vision models, browser WASM demo, and standardized trichoscopy data validation pipelines.
* **[Ultralytics YOLO11 / YOLOv8](https://github.com/ultralytics/ultralytics)** — Open computer vision object detection framework.
* **[ONNX Runtime Web (`onnxruntime-web`)](https://github.com/microsoft/onnxruntime)** — Cross-platform, client-side WebAssembly and WebGPU machine learning inference.
* **[ROS 2 (Robot Operating System)](https://github.com/ros2)** — Industry standard deterministic middleware for multi-axis robotic arms and surgical visual servoing.
* **[OpenCV](https://github.com/opencv/opencv)** — Open Source Computer Vision Library for optical camera calibration and homography.

---

### Contributing to this Research Library
Found a new paper, open dataset, or robotics project? Submit a pull request or open an issue in [github.com/openhairstack/.github](https://github.com/openhairstack/.github).
