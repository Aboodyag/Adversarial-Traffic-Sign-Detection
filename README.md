

- Built for CS4452

- # Adversarial Traffic Sign Detection

Training and evaluating YOLOv8 object detection models for robustness against **physical adversarial attacks** on traffic signs — the kind of real-world tampering (stickers, graffiti, tape) that can fool a self-driving car's perception system.

## Overview

Traffic sign recognition is a core part of autonomous driving perception, but real-world signs aren't pristine — they get vandalized, weathered, and occasionally deliberately altered to fool computer vision systems. This project studies how vulnerable a modern object detector (YOLOv8) is to these kinds of physical adversarial attacks, and whether adversarial training can close the gap.

A YOLOv8 model was trained and evaluated on a 264-class traffic sign dataset, then stress-tested against four categories of physical attacks: tape, patches, graffiti, and altered illumination. Adversarial training was then applied and evaluated across multiple dataset configurations to see how much robustness could be recovered.

## Key Results

- Evaluated across a **264-class traffic sign dataset**
- Tested **4 physical attack types**: tape, patch, graffiti, and illumination-based tampering
- Adversarial training improved **mAP50** robustness under attack conditions compared to the baseline model
- Findings written up in an **IEEE-style research publication**

## Tech Stack

- Python
- PyTorch
- Ultralytics YOLO (YOLOv8)
- Google Colab (training environment)
- Computer vision / image augmentation workflows

## Getting Started

```bash
git clone https://github.com/Aboodyag/Adversarial-Traffic-Sign-Detection.git
cd Adversarial-Traffic-Sign-Detection
pip install -r requirements.txt   # or: pip install ultralytics torch torchvision
```

The training and evaluation workflow is set up as a notebook, designed to run in **Google Colab** (GPU runtime recommended) — open the `.ipynb` file directly in Colab, or run it locally with a CUDA-enabled GPU and Jupyter installed.

Typical workflow inside the notebook:
1. Load and preprocess the traffic sign dataset
2. Train the baseline YOLOv8 model
3. Generate adversarial examples (tape / patch / graffiti / illumination attacks)
4. Evaluate baseline vs. adversarially-trained model on mAP50 under each attack type

> If a `requirements.txt` isn't present in the repo, the core dependencies are `ultralytics`, `torch`, `torchvision`, and standard CV libraries (`opencv-python`, `numpy`, `matplotlib`).
