Shadow-Removal-and-Intrinsic-Images

This project explores shadow removal in handwritten documents using two approaches:
(1) a learning-based method inspired by BEDSR-Net, and
(2) intrinsic image decomposition with colorful diffuse shading.

Shadow detection is applied to intrinsic image components to evaluate which best highlights shadows for effective removal.

Execution Instructions
1. Intrinsic Image Decomposition & Shadow Detection

Open and run Project_2_AP.ipynb

Modify the image directory paths for intrinsic image decomposition and shadow segmentation

2. Shadow Removal (BEDSR-Net)
Required Files

infer.py

dataset.py

dataset_csv.py

results/

Install Dependencies

pip install --upgrade albumentations matplotlib wandb pytorch-gradcam
pip install --upgrade torch torchvision
pip install torch==2.4.0 torchvision==0.19.0 torchaudio==2.4.0 --index-url https://download.pytorch.org/whl/cu121

Dataset Preparation

python make_dataset.py
Modify the CSV generation inside the script from validation to test.

Training

python3 BEDSR-Net-Reimplementation/train_benet.py --config ./BEDSR-Net-Reimplementation/configs/model=benet/config.yaml

python3 BEDSR-Net-Reimplementation/train_bedsrnet.py --config ./BEDSR-Net-Reimplementation/configs/model=bedsrnet/config.yaml

Inference

python3 infer.py

(Optional) Zip Results

zip -r shadow_removal.zip BEDSR-Net-Reimplementation

References

BEDSR-Net: Lin et al., 2020

Colorful Diffuse Intrinsic Image Decomposition: Careaga & Aksoy, 2024
