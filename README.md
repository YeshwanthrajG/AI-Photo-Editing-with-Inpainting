<div align="center">

# 🖼️ AI Photo Editing with Inpainting

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python" />
  <img src="https://img.shields.io/badge/PyTorch-2.0-EE4C2C?style=for-the-badge&logo=pytorch" />
  <img src="https://img.shields.io/badge/Stable%20Diffusion-XL-blueviolet?style=for-the-badge" />
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Gradio-UI-orange?style=for-the-badge&logo=gradio" />
</p>

<p align="center">
  <strong>Intelligent AI-powered photo editing using Segment Anything Model (SAM) + Stable Diffusion XL Inpainting.</strong><br/>
  Select any subject in an image - change its background, replace the subject, or remove objects entirely - using natural language prompts.
</p>

</div>

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Demo](#-demo)
- [Features](#-features)
- [Architecture](#-architecture)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running the App](#running-the-app)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [License](#-license)
- [Author](#-author)

---

## 🧠 Overview

**AI Photo Editing with Inpainting** is a generative AI application that enables intelligent, prompt-driven image editing without manual masking tools. By combining Meta's **Segment Anything Model (SAM)** for precise object segmentation and **Stable Diffusion XL Inpainting** for content generation, users can:

- Select a subject with a simple point-click
- Describe the desired change as a text prompt
- Receive a photorealistic edited image in seconds

This project was developed as part of the **Udacity Generative AI Nanodegree** and showcases applied computer vision and generative AI at the intersection of diffusion models and segmentation.

---

## 🎬 Demo

> Upload an image → Click to select a subject → Enter a text prompt → Get your edited photo

**Example Use Cases:**
- 🚗 Car on a highway → Change background to a mountain road
- 🐕 Dog in a living room → Replace background with a forest
- 🎭 Portrait → Swap subject outfit or location

---

## ✨ Features

- **Zero-manual-masking**: SAM auto-generates precise segmentation masks from point inputs
- **Dual editing modes**: Change background *or* replace the subject
- **Text-prompt driven**: Describe your desired output in plain English
- **Interactive Gradio UI**: Web-based interface accessible via public URL
- **GPU-accelerated inference**: Runs on `float16` for optimal performance

---

## 🏗️ Architecture

```
User Input (Image + Point + Text Prompt)
         │
         ▼
┌─────────────────────┐
│  SAM (Segment       │  ◄── Facebook/Meta ViT-H
│  Anything Model)    │       Point-based masking
└────────┬────────────┘
         │  Segmentation Mask
         ▼
┌─────────────────────┐
│  SDXL Inpainting    │  ◄── diffusers AutoPipeline
│  Pipeline           │       Text-conditioned fill
└────────┬────────────┘
         │
         ▼
   Edited Output Image
```

---

## 🛠️ Tech Stack

| Category | Technology |
|---|---|
| Language | Python 3.10+ |
| Deep Learning | PyTorch 2.0, `torch.float16` |
| Segmentation | Meta SAM (`facebook/sam-vit-huge`) |
| Image Generation | Stable Diffusion XL (`diffusers/stable-diffusion-xl-1.0-inpainting-0.1`) |
| Diffusion Library | HuggingFace `diffusers`, `transformers` |
| UI | Gradio |
| Notebook | Jupyter |
| Environment | Conda / pip |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10 or higher
- CUDA-capable GPU (recommended: 8GB+ VRAM)
- Conda or pip environment manager
- HuggingFace account (for model access)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/YeshwanthrajG/AI-Photo-Editing-with-Inpainting.git
cd AI-Photo-Editing-with-Inpainting

# 2. Create and activate a virtual environment
conda create -n inpainting python=3.10
conda activate inpainting

# 3. Install dependencies
pip install -r requirements.txt
```

**Core dependencies (`requirements.txt`):**
All required Python packages are listed in:
[requirements.txt](./requirements.txt)

```bash
pip install -r requirements.txt
```

### Running the App

```bash
# Launch Jupyter Notebook
jupyter notebook

# Open the main notebook and run all cells
# The Gradio interface will launch with a public shareable URL
```

---

## 📖 Usage

1. **Upload** your source image in the Gradio interface
2. **Click** on the subject you want to edit (point-based selection)
3. SAM generates a **segmentation mask** around the selected area
4. **Enter a text prompt** describing the desired result (e.g., `"sunset beach background"`)
5. Hit **Generate** - the inpainting model fills the masked region according to your prompt
6. **Download** your edited image

> 💡 Tip: For best results, use descriptive prompts and choose high-contrast subjects.

---

## 📁 Project Structure

```
AI-Photo-Editing-with-Inpainting/
├── notebook.ipynb          # Main project notebook
├── requirements.txt        # Python dependencies
├── assets/                 # Sample images for testing
└── README.md               # Project documentation
```

---

## 📄 License

This project is licensed under the [LICENSE](./LICENSE).

---

## 👤 Author

**Yeshwanthraj G**

- 🐙 GitHub: [@YeshwanthrajG](https://github.com/YeshwanthrajG)
