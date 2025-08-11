# Audio CNN

## Overview

Big thanks to [Andreas Trolle](https://www.linkedin.com/in/andreas-trolle-a04aa8192/) for the course [Deep Learning for Audio](https://youtu.be/KLYfwigQPuY?si=QEQOPwMtzMF_8c0q). You can check out his youtube video for more information about how to build a CNN for audio classification.

In this project, I built a CNN for audio classification using PyTorch, train and deploy it using Modal. The dataset of this project will be [ESC-50](https://github.com/karolpiczak/ESC-50). The frontend will be made using Next.js with shadcn/ui.

## Features:

- Custom CNN model for sound classification
- ResNet-style architecture with residual blocks
- Mel-spectrogram feature extraction
- Data augmentation using data mixing
- Serverless GPU inference using Modal
- Simple Next.js frontend to visualize the results and processes
- Realtime audio classification with 80%+ accuracy

## Installation

### Clone the repository
```bash
git clone https://github.com/iqbal89co/sound-classification-cnn
```

### Install Python

Download and install Python if not already installed. Use the link below for guidance on installation:
[Python Download](https://www.python.org/downloads/)

Create a virtual environment with **Python 3.12**.

### Backend

Navigate to folder:

```bash
cd sound-classification-cnn
```

Create virtual environment:

```bash
python -m venv .venv
```

Activate virtual environment:

```bash
.venv\Scripts\activate
```

Install PIP:

```bash
python -m ensurepip --upgrade
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Modal setup:
Please make sure you have registered Modal account. If not, please register it from [Modal](https://modal.com).

```bash
modal setup
```

Run on Modal:

```bash
modal run main.py
```

Deploy backend:

```bash
modal deploy main.py
```

### Frontend

Make sure nodejs is installed. Use the link below for guidance on installation:
[NodeJS Download](https://nodejs.org/en/download/)

Navigate to folder:

```bash
cd audio-cnn-viz
```

Install dependencies:

```bash
npm install
```

Create .env file:

```bash
cp .env.example .env
```

Fill the .env file with your Modal API Url you get after running `modal deploy main.py`.
```bash
NEXT_PUBLIC_MODEL_TEST_URL=your-modal-api-url
```

Run frontend:

```bash
npm run dev
```