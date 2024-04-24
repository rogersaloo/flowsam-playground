# Description
Play ground implementation of [flowsam](https://arxiv.org/pdf/2404.12389.pdf) a moving object segmentation model using SAM and optical flow.

Adopted from [flowsam](https://github.com/Jyxarthur/flowsam) and segment anything repo [here](https://github.com/facebookresearch/segment-anything/)


## Installation
1. Create virtual environment `python -m venv .venv`
2. Install pytorch. Depending on the GPU and Cuda navigate to the pytorch site [here](https://pytorch.org/) and install with pip.
    ```
    pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
    ```
3. Install the requirements `pip install -r requirements.txt`
4. Install segment anything [here](https://github.com/facebookresearch/segment-anything/) 
    ```
    pip install git+https://github.com/facebookresearch/segment-anything.git
    ```


## Get started 
### Running inference 
1. In the dataset directory create both tht optical flow and the RGB images inorder to test on th eflow of the images.
    - The flow images need to be png format 
    - the RGB images need to be png format
2. The following used a smaple dataset evaluation on a custom images
    ```
    python flowsam/evaluation.py --model=flowpsam --dataset=example --flow_gaps=1,-1,2,-2     --max_obj=10 --num_gridside=20 --ckpt_path=checkpoints/frame_level_flowpsam_vitbvith_train_on_oclrsyn_dvs16.pth --save_path=./results
    ```
