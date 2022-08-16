commands I used to get it working.

```sh
git clone git@github.com:aldopareja/DeepIM-PyTorch.git
conda create -n deepIM
conda activate deepIM
conda install python=3.8.1
pip install torch==1.8.2 torchvision==0.9.2 --extra-index-url https://download.pytorch.org/whl/lts/1.8/cu102
pip install -r requirement.txt
unzip models2.zip
mv models DeepIM-PyTorch/data/
unzip checkpoinst2.zip
mv checkpoints DeepIM-PyTorch/data/
cd DeepIM-PyTorch/lib/point_matching_loss/
python setup.py install
cd ../utils/
python setup.py build_ext --inplace
sudo apt-get install build-essential cmake pkg-config libx11-dev libatlas-base-dev libgtk-3-dev  libboost-python-dev libassimp-dev -y
git submodule update --init --recursive
cd ycb_render/
sudo /home/aldo/miniconda3/envs/deepIM/bin/python setup.py develop
pip install pyyaml==5.4.1
./experiments/scripts/demo_rgbd.sh
```