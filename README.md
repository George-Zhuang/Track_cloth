# NetTrack


## :hammer_and_wrench: Install 

**Prerequisite**
```bash
conda create -n nettrack python=3.10 # please use the default version
pip3 install torch torchvision # --index-url https://download.pytorch.org/whl/cu121
pip3 install -r requirements.txt
pip3 install cython; pip3 install 'git+https://github.com/cocodataset/cocoapi.git#subdirectory=PythonAPI'
pip3 install cython_bbox
sudo apt update
sudo apt install ffmpeg
```

Install Grounding DINO, CoTracker, and ByteTrack:
```bash
pip install git+https://github.com/IDEA-Research/GroundingDINO.git
pip install git+https://github.com/facebookresearch/co-tracker.git
```

**Prepare weights:**
Download the default pretrained Grouding DINO and CoTracker model:
```bash
cd weights
cd groundingdino
wget https://huggingface.co/ShilongLiu/GroundingDINO/resolve/main/groundingdino_swinb_cogcoor.pth
cd ..
mkdir cotracker && cd cotracker
wget https://dl.fbaipublicfiles.com/cotracker/cotracker_stride_4_wind_8.pth
cd ..
```

**(Optional) Prepare BFT:**
```bash
mkdir data && cd data
mkdir bft && cd bft
# download bft dataset from the anonymous link https://mega.nz/folder/ZqdjwSrB#m5dvU5ioCuYfR0L63xX1Hg
cd ..
```

## :arrow_forward: Demo
Run demo with python!
```bash
sh tools/demo/demo_seq.sh
```
The results will be shown in ```./data/demo/track_res```.

## :pray: Appreciation
We appreciate your efforts to make this work better!