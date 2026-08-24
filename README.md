# 🎨 AI Image & Video Generation Tools

A curated collection of Google Colab notebooks for experimenting with cutting-edge AI image and video generation models, featuring **Fooocus-Lite**, **Flux**, and **Stable Diffusion**.

---

## 📋 Table of Contents

- [Quick Start](#quick-start)
- [Available Tools](#available-tools)
- [Getting Started](#getting-started)
- [Requirements & Setup](#requirements--setup)
- [Troubleshooting](#troubleshooting)
- [Credits](#credits)

---

## 🚀 Quick Start

1. **Choose a notebook** from the [Available Tools](#available-tools) section below
2. **Click the "Open in Colab" link** or upload the notebook to Google Colab
3. **Run all cells** (Runtime → Run all, or Ctrl+F9)
4. **Wait for the Gradio interface** to load (check the output cell for the public URL)
5. **Generate images/videos** using the web interface

⏱️ **First run:** 5-10 minutes (downloads models and dependencies)
⏱️ **Subsequent runs:** 2-5 minutes (models cached)

---

## 📚 Available Tools

### 1. **Fooocus-Lite** (Recommended for Beginners)
**File:** `notebooks/fooocus_livedraw.ipynb`

**What it does:** Interactive image generation with a lightweight, beginner-friendly interface

**Features:**
- Real-time image generation
- Easy-to-use Gradio web interface  
- Optimized for Google Colab's T4 GPU
- Good balance of speed and quality

**Best for:** Quick experimentation, learning, interactive generation

**Runtime:** ~2-5 minutes per image

**GPU Requirements:** T4 (free tier) ✅ or better

**[Open in Colab →](https://colab.research.google.com/github/DonMilcrypto/DonMilcrypto/blob/main/notebooks/fooocus_livedraw.ipynb)**

---

### 2. **Flux** (Most Advanced)
**File:** `notebooks/flux.ipynb`

**What it does:** State-of-the-art image generation using Black Forest Labs' Flux model

**Features:**
- High-quality image generation
- Advanced control with `--always-high-vram` mode
- Latest text-to-image AI
- Requires slightly more resources

**Best for:** High-quality outputs, exploring cutting-edge models

**Runtime:** ~3-7 minutes per image

**GPU Requirements:** T4+ recommended (works on free tier but slower)

**[Open in Colab →](https://colab.research.google.com/github/DonMilcrypto/DonMilcrypto/blob/main/notebooks/flux.ipynb)**

---

### 3. **Stable Diffusion Videos** (Advanced)
**File:** `stable_diffusion_videos.ipynb`

**What it does:** Generate smooth videos by interpolating between prompts

**Features:**
- Latent space interpolation for smooth transitions
- Music video generation (experimental)
- Reproducible generation with seed control
- Interface-based or programmatic usage

**Best for:** Creating video content, morphing between concepts

**Runtime:** ~5-15 minutes per video (varies by frame count)

**GPU Requirements:** T4+ recommended

**[Open in Colab →](https://colab.research.google.com/github/DonMilcrypto/DonMilcrypto/blob/main/stable_diffusion_videos.ipynb)**

---

## 🛠️ Getting Started

### Prerequisites
- ✅ **Free Google Account** (no paid tier needed)
- ✅ **Google Colab access** (colab.research.google.com)
- ✅ **Basic understanding of ML/AI** (helpful but not required)

### Step-by-Step Setup

1. **Open Notebook in Colab**
   - Click any notebook link above
   - Or upload `.ipynb` file to your Google Drive → Right-click → Open with → Google Colaboratory

2. **Check Runtime Settings**
   - Go to `Runtime` → `Change runtime type`
   - Select `GPU` (T4 preferred, A100 if available)
   - Click `Save`

3. **Run Installation Cells**
   - Execute the first 2-3 cells (installs dependencies)
   - Watch for errors — if conda/pip fails, re-run the cell

4. **Launch the Interface**
   - Find the Gradio app link in the output (looks like `https://abc123.gradio.app`)
   - Click it to open the full-screen interface
   - **Note:** Link expires after ~1 hour; re-run the cell if needed

5. **Generate Content**
   - Enter prompts and adjust settings
   - Hit **Generate**
   - Download outputs or save to Google Drive (if connected)

---

## ⚙️ Requirements & Setup

### System Requirements
| Component | Minimum | Recommended |
|-----------|---------|------------|
| GPU | T4 (free) | A100, H100 |
| RAM | 4GB | 8GB+ |
| Storage | 5GB+ | 10GB+ |
| Time | 2 min | Instant (cached) |

### GPU Memory Usage
- **Fooocus-Lite:** ~6GB
- **Flux:** ~8GB  
- **Stable Diffusion Videos:** ~8-10GB

All fit comfortably on T4 (16GB VRAM).

### Python Environment
- Python 3.10+ (configured in notebooks)
- PyTorch with CUDA support
- Gradio for web interface
- Various ML libraries (diffusers, transformers, etc.)

---

## 🐛 Troubleshooting

### Common Issues

#### 1. **"CUDA out of memory" error**
```
RuntimeError: CUDA out of memory
```
**Solution:**
- Restart runtime: `Runtime` → `Restart runtime`
- Reduce image resolution (512 instead of 768)
- Clear GPU cache: add `import torch; torch.cuda.empty_cache()` cell
- Use a different instance (refresh page and try again)

#### 2. **"No module named X" error**
```
ModuleNotFoundError: No module named 'fooocus'
```
**Solution:**
- Re-run the installation cells (first 3 cells)
- Restart runtime before running inference cells
- Check internet connection

#### 3. **Gradio Link Not Working**
**Solution:**
- The link expires after ~1 hour; re-run the launch cell to generate a new one
- Make sure `share=True` is set in the launch command
- Check your firewall/VPN isn't blocking gradio.app

#### 4. **Slow Generation**
**Solution:**
- First run is always slower (model download + initialization)
- Subsequent runs are cached (~2-3x faster)
- Upgrade to A100 GPU if available
- Reduce resolution or num_inference_steps

#### 5. **"Invalid CUDA version" warnings**
**Solution:**
- These are usually safe to ignore; Colab manages CUDA versions
- If generation fails, restart runtime and try again

---

## 📖 Advanced Usage

### Save to Google Drive
Most notebooks include a cell to mount Google Drive:
```python
from google.colab import drive
drive.mount('/content/gdrive')
```

Then use paths like: `/content/gdrive/MyDrive/outputs/`

### Download Results
- Click the **Download** button in Gradio interface, OR
- Use Colab's Files panel (left sidebar) to download files locally

### Custom Settings
Each notebook allows you to adjust:
- **Resolution:** 512, 768, 1024 (larger = slower, higher quality)
- **Inference steps:** 20-50 (more steps = slower, better quality)
- **Guidance scale:** 7-15 (controls adherence to prompt)
- **Seed:** Set for reproducibility

---

## 🏠 Repository Structure

```
DonMilcrypto/
├── README.md                           # This file
├── QUICKSTART.md                       # 5-minute setup guide
├── notebooks/
│   ├── fooocus_livedraw.ipynb         # ⭐ Start here!
│   └── flux.ipynb                     # Advanced image generation
├── quickstarts/
│   └── (future: minimal/beginner versions)
└── stable_diffusion_videos.ipynb      # Video generation
```

---

## 📝 Notes for Developers

If you're modifying or enhancing these notebooks:

1. **Test in Colab** (free tier) before committing
2. **Document assumptions:** Python version, required GPU, expected runtime
3. **Add error handling:** Use try/except for setup steps
4. **Version dependencies:** Pin versions in pip/conda commands
5. **Clean up:** Remove Colab-specific cells before uploading (e.g., test cells)

---

## 🙏 Credits & Attribution

- **Fooocus-Lite:** [brayevalerien/Fooocus-Lite](https://github.com/brayevalerien/Fooocus-Lite)
- **Flux:** [Black Forest Labs](https://github.com/black-forest-labs/flux)
- **Stable Diffusion Videos:** [nateraw/stable-diffusion-videos](https://github.com/nateraw/stable-diffusion-videos)
- **Stable Diffusion:** [CompVis/stable-diffusion](https://github.com/CompVis/stable-diffusion)

---

## 📧 Support & Feedback

Found a bug or have a feature request? Open an issue or reach out!

---

**Happy generating! 🎨✨**

*Last updated: 2026-08-24*
