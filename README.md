# 🧪 MLLM-Image Corruption
**Evaluating and Analyzing the Robustness of Multimodal Large Language Models under Image Corruption**

This repository provides code and tools for reproducing the robustness benchmark of Multimodal LLMs (MLLMs) under various types of image corruption, as described in our paper.

## 📌 Highlights

- 🌪️ **Hierarchical Image Corruption Benchmark (MLLM-IC)**: Evaluates models across **severity**, **capability**, and **corruption** dimensions.
- 🧠 **11 SOTA MLLMs Evaluated**: Including LLaVA-1.5, DeepSeek-VL, Transcore-M, GPT-4o, Gemini 2.0, and more.
- 📊 **Comprehensive Visualizations**: Radar charts, heatmaps, and sensitivity maps to facilitate fine-grained analysis.

## 📂 Project Structure

- `benchmark/`: Benchmark execution and evaluation.
- `corruptions/`: Generation of various image corruption types.

## 📦 Dataset & Benchmark

We provide a streamlined MLLM-IC-mini subset for quick evaluation. The full MLLM-IC Benchmark (more than 300GB) is not hosted in this repository due to its size.

| Resource                 | Description                               | Status                      |
| ------------------------ | ----------------------------------------- | --------------------------- |
| 📦 MLLM-IC (Full)        | Full benchmark. Not hosted here. | —                           |
| 📥 MLLM-IC-mini (Subset) | Lightweight version for fast evaluation.  | ✅ Available in **Releases** |


## 🖼️ Corruption Dimensions

To comprehensively evaluate the visual robustness of Multimodal Large Language Models (MLLMs), we categorize 40+ image corruption types into a **three-level taxonomy** based on their formation mechanism: **Global**, **Region**, and **Pixel Level**. This allows us to analyze model sensitivity at multiple operational scales.

### Global-Level Corruptions

These corruptions affect the **entire image** uniformly. They typically change overall image structure, geometry, or tone distribution.

| Category             | Corruption Types                                                              |
|----------------------|-------------------------------------------------------------------------------|
| **Color Channel**     | Brightness, Contrast, Saturation, Invert, GammaContrast, Channel Shuffle     |
| **Geometric Transform** | Scale (x, y, xy), Shear (x, y, xy), Rotate                                   |
| **Blur**              | Defocus Blur, Glass Blur, Zoom Blur, Motion Blur, Gaussian Blur              |
| **Texture Changing**  | Canny Edge, Sharpen, Cartoon                                                  |


### Region-Level Corruptions

These perturbations affect **localized image areas**, simulating real-world scenarios such as occlusion or partial degradation.

| Category             | Corruption Types                                                              |
|----------------------|-------------------------------------------------------------------------------|
| **Occlusion**         | Cutout, Coarse Dropout                                                        |
| **Compression**       | Average Pooling, Max Pooling, Pixelation, JPEG Compression                   |
| **Weather Condition** | Snow, Frost, Fog, Rain, Snowflake, Spatter                                   |
| **Shape Changing**    | Elastic Transform, Jigsaw, Piecewise Affine                                  |


### Pixel-Level Corruptions

These simulate **low-level noise** often encountered in sensor degradation or transmission errors.

| Category    | Corruption Types                                                       |
|-------------|------------------------------------------------------------------------|
| **Noise**   | Impulse Noise, Shot Noise, Speckle Noise, Gaussian Noise, Poisson Noise |


### Why Corruption Dimensions Matter

- ✅ **Diagnostic Power**: Understand which corruption types most significantly impact model performance.
- ✅ **Sensitivity Tracking**: Reveal per-model vulnerability under different corruptions.
- ✅ **Benchmark Fidelity**: Provide task-level robustness insights relevant to real-world deployment.


## 🧠 Capability Dimensions

To assess the robustness of Multimodal Large Language Models (MLLMs) under corrupted visual conditions, we adopt a **hierarchical capability framework** that decomposes model ability into **Perception** and **Reasoning**, each with mid- and low-level subskills.

### Perception Capabilities

| Mid-Level Capability         | Low-Level Skills                                                                 |
|-----------------------------|-----------------------------------------------------------------------------------|
| **Global Context Sensing**  | Image Topic, Image Quality, Image Emotion, Image Scene, Image Style, Scene Understanding |
| **Instance & Part Recognition** | Instance Identity, Attribute Recognition, Instance Interaction, Instance Attribute, Emotion Recognition, Action Recognition, Celebrity Recognition, Landmark Recognition |
| **Spatial Perception**      | Physical Relation, Instance Location, Instance Counting, Spatial Relation, Object Localization |


### Reasoning Capabilities

| Mid-Level Capability         | Low-Level Skills                                                                 |
|-----------------------------|-----------------------------------------------------------------------------------|
| **Knowledge Reasoning**     | Chart Understanding, Science Knowledge, Nature Relation, Structured Image-Text Understanding, Visual Mathematics, Function Reasoning, Physical Property Reasoning |
| **Logic Reasoning**         | Visual Reasoning, Visual Referring Expression, Social Relation, Identity Reasoning, Future Prediction, Attribute Comparison, Text Recognition, OCR |


### Why Capability Dimensions Matter

- ✅ **Fine-Grained Analysis**: Goes beyond aggregate accuracy to reveal how specific abilities degrade under corruption.
- ✅ **Model Differentiation**: For example, DeepSeek-VL excels at global context and logic reasoning, while Transcore-M is strong in part-level recognition.
- ✅ **Robustness Diagnosis**: Helps identify which model capabilities are more vulnerable to which types of image corruption (e.g., blur vs. occlusion).

### 🔖 BibTeX

```bibtex
@article{Qiu2025mllmic,
  title     = {Benchmarking Multimodal Large Language Models Against Image Corruptions},
  author    = {Xinkuan Qiu, Meina Kan, Yongbin Zhou, Shiguang Shan},
  journal   = {Proceedings of the IEEE/CVF International Conference on Computer Vision (ICCV)},
  year      = {2025},
}
