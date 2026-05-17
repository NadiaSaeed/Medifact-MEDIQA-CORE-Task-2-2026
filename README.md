# Medifact-MEDIQA-CORE-Task-2-2026
Interaction-Aware Multimodal Fusion for Fine-Grained Radiology Report Discrepancy Analysis
<div align="center">

<div align="center">

## ⭐ If you find this work useful, please consider starring the repository ⭐

<img src="https://readme-typing-svg.demolab.com/?pause=1000&size=24&center=true&vCenter=true&width=900&height=60&color=58A6FF&lines=Multimodal+Medical+AI;Radiology+Discrepancy+Reasoning;Clinical+Vision-Language+Learning" />

</div>
<p align="center">
  <img src="https://img.shields.io/badge/Competition-ImageCLEFmed%20MEDIQA--CORE%202026-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Rank-🥈%202nd%20Place-gold?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Framework-PyTorch-red?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Multimodal-CT%20%2B%20Clinical%20Text-success?style=for-the-badge"/>
</p>

---


### Official Solution for MEDIQA-CORE Task 2 — ImageCLEFmed 2026

</div>

---

# 📌 Overview

This repository contains our **2nd place solution** for the **ImageCLEFmed MEDIQA-CORE 2026 Task 2** challenge on **multimodal radiology report discrepancy analysis**.

The task focuses on identifying and reasoning about discrepancies between:

- 🧠 **3D Abdominal CT Volumes**
- 📝 **Preliminary Radiology Reports**
- ✏️ **Candidate Report Edits**

Our framework jointly reasons over imaging and clinical text to:

✅ Predict image-level agreement  
✅ Assess discrepancy severity  
✅ Classify edit type  

---

# 🚀 Key Contributions

✨ **Interaction-Aware Fusion**  
Explicit semantic interaction modeling between original reports and candidate edits.

✨ **Robust CT Processing**  
HU normalization, multi-series fallback, anti-aliased resizing, and standardized volumetric construction.

✨ **Contextual Clinical Text Embeddings**  
Mean-pooled transformer embeddings using **DeBERTa-v3**.

✨ **Balanced Multimodal Learning**  
Weighted CT fusion prevents imaging dominance over discrepancy semantics.

✨ **Stabilized Multitask Optimization**  
LayerNorm, gradient clipping, weighted multitask learning, and robust inference consistency.

---

# 🩻 CT Processing Pipeline

```text
DICOM Slices
     ↓
HU Conversion
     ↓
Intensity Clipping
     ↓
Normalization
     ↓
Slice Sampling
     ↓
3D CNN Encoder
```

### Features
- Multi-series fallback
- Robust missing scan handling
- Fixed-size volumetric representation
- Efficient float32 inference pipeline

---

# 📝 Clinical Text Processing

We employ:

- 🧠 DeBERTa-v3-base
- 📚 Mean pooling
- 🔄 L2 normalization
- ⚡ Empty-text handling

to produce contextual clinical embeddings optimized for discrepancy analysis.

---

# 🏗️ Multimodal Fusion

Final representation:

```math
x = [r \;||\; e \;||\; d \;||\; p \;||\; 0.3c]
```

where:

| Symbol | Description |
|---|---|
| `r` | Report embedding |
| `e` | Edit embedding |
| `d` | Difference interaction |
| `p` | Element-wise interaction |
| `c` | CT embedding |

---

# 🎯 Multitask Learning

The framework jointly predicts:

| Task | Description |
|---|---|
| Agreement | Whether edit matches CT findings |
| Severity | Clinical significance of discrepancy |
| Edit Type | Correction / Addition / Clarification |

Loss function:

```math
\mathcal{L}=1.5\mathcal{L}_a+1.2\mathcal{L}_s+1.0\mathcal{L}_e
```

---

# 🏆 Competition Result

<div align="center">

| Challenge | Rank |
|---|---|
| ImageCLEFmed MEDIQA-CORE Task 2 2026 | 🥈 2nd Place |

</div>

---

# 📖 Citation

```bibtex
@article{medifact2026mediqacore,
  title={MediFact at MEDIQA-CORE-Task-2 2026: Interaction-Aware Multimodal Fusion for Fine-Grained Radiology Report Discrepancy Analysis},
  author={Nadia Saeed},
  journal={ImageCLEFmed MEDIQA-CORE 2026},
  year={2026}
}
```

---

# 🤝 Acknowledgements

We thank the organizers of:

- MEDIQA-CORE 2026
- ImageCLEFmed
- Clinical experts and annotators

for providing the benchmark dataset and evaluation framework.

---

