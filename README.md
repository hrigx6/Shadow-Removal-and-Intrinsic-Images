# Shadow-Removal-and-Intrinsic-Images
Explores shadow removal in handwritten documents using two approaches: a learning-based method inspired by BEDSR-Net and intrinsic image decomposition with colorful diffuse shading. Shadow detection is applied to intrinsic components to evaluate which best highlights shadows for removal.

EXECUTION INSTRUCTIONS:

1)Run the Project_2_AP.ipynb file while modifying the image directory for intrinsic image decomposition and shadow segmentation


2) For shadow_removal we have attached the following files.
-infer.py
-dataset_csv.py
-dataset.py
-results


To RUN- 

!pip install --upgrade albumentations
!pip install --upgrade matplotlib
!pip install --upgrade torch torchvision
!pip install torch==2.4.0 torchvision==0.19.0 torchaudio==2.4.0 --index-url https://download.pytorch.org/whl/cu121
!pip install wandb
!pip install pytorch-gradcam

!python make_dataset.py 
#Make changes to the code from Val to test to make csv

!python3 BEDSR-Net-Reimplementation/train_benet.py --config ./BEDSR-Net-Reimplementation/configs/model\=benet/config.yaml

!python3 /content/BEDSR-Net-Reimplementation/train_bedsrnet.py --config /content/BEDSR-Net-Reimplementation/configs/model=bedsrnet/config.yaml

!python3 infer.py

!zip -r shadow_removal.zip /content/BEDSR-Net-Reimplementation
