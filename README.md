# Mac M1  Huggingface Diffusers Demo

Demo of how to get HuggingFace Diffusers working on an M1 Mac.

This uses the [MPS branch](https://github.com/huggingface/diffusers/tree/mps) for acceleration support. This is under heavy development so things are likely to break. 

These instructions are correct as of 7 Sep 2022. On a 2022 MBP M1 Max with 32Gb RAM I get 1.53 it/s, which compares to roughly 2.0 on a T4 Tesla on Google Collab

## Installation

### Install Python

Install Python from https://www.python.org/downloads/macos/ (Yes, that installer is now better than brew)

### Setup 

```

# Get the code 
git clone https://github.com/nlothian/m1_huggingface_diffusers_demo.git

# Create and activate a virtual envionment
python3 -m venv ./venv
source ./venv/bin/activate

# Install depedencies (including the MPS of HuggingFace Diffusers)
pip install -r requirements.txt

# Deactivate and rectivate the virtual envionment to make sure we are using the correct Jupyter
deactivate
source ./venv/bin/activate

# Enable CPU fallback for the M1 GPU
export PYTORCH_ENABLE_MPS_FALLBACK=1

# Run Jupyter
jupyter notebook
```

This will open your browser. You can now open `StableDiffusion Demo.ipynb` and try it for yourself. 


