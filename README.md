## ___***ToonCrafter_with_SketchGuidance***___
This repository is an implementation that recreates the SketchGuidance feature of "ToonCrafter".

- https://github.com/ToonCrafter/ToonCrafter
- https://arxiv.org/pdf/2405.17933

https://github.com/user-attachments/assets/f72f287d-f848-4982-8f91-43c49d037007

# ToonCrafter with Sketch Guidance

## Overview
This repository contains the ToonCrafter model with additional sketch guidance functionality. The model is hosted on GitHub and can be accessed via the following link:

- **Repository:** [https://github.com/svjack/ToonCrafter_with_SketchGuidance](https://github.com/svjack/ToonCrafter_with_SketchGuidance)

## Installation

### Clone the Repository
To clone the repository and set up the environment, follow these steps:

```bash
git clone https://github.com/svjack/ToonCrafter_with_SketchGuidance && cd ToonCrafter_with_SketchGuidance
```

### List Control Models
After cloning the repository, you can list the control models available:

```bash
ls control_models
```

### Download Sketch Encoder
Download the `sketch_encoder.ckpt` file from the Hugging Face repository:

```bash
wget https://huggingface.co/Doubiiu/ToonCrafter/resolve/main/sketch_encoder.ckpt
```

### Copy Sketch Encoder to Control Models
Move the downloaded `sketch_encoder.ckpt` file to the `control_models` directory:

```bash
cp sketch_encoder.ckpt control_models
```

## Usage

### Run the Gradio App
Once the repository is cloned and the necessary files are in place, you can run the Gradio app using the following command:

```bash
python gradio_app.py
```

This will start the Gradio interface, allowing you to interact with the ToonCrafter model with sketch guidance.

## 🧰 Models

|Model|Resolution|GPU Mem. & Inference Time (A100, ddim 50steps)|Checkpoint|
|:---------|:---------|:--------|:--------|
|ToonCrafter_512|320x512| TBD (`perframe_ae=True`)|[Hugging Face](https://huggingface.co/Doubiiu/ToonCrafter/blob/main/model.ckpt)|
|SketchEncoder|TBD| TBD |[Hugging Face](https://huggingface.co/Doubiiu/ToonCrafter/blob/main/sketch_encoder.ckpt)|


Currently, ToonCrafter can support generating videos of up to 16 frames with a resolution of 512x320. The inference time can be reduced by using fewer DDIM steps.



## ⚙️ Setup

### Install Environment via Anaconda (Recommended)
```bash
conda create -n tooncrafter python=3.8.5
conda activate tooncrafter
pip install -r requirements.txt
```


## 💫 Inference

### 1. Local Gradio demo
1. Download pretrained ToonCrafter_512 and put the model.ckpt in checkpoints/tooncrafter_512_interp_v1/model.ckpt.
2. Download pretrained SketchEncoder and put the model.ckpt in control_models/sketch_encoder.ckpt.

```bash
  python gradio_app.py 
```
