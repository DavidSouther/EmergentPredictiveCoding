* GCP: 
  * Zone: us-central1-*
  * Family: GPU A2 a2-highgpu-1g
  * GPU: A100 GPU x1
  * Boot disk: Ubuntu 20.04 LTS
* GCP: [Install CUDA](https://cloud.google.com/compute/docs/gpus/install-drivers-gpu#ubuntu-driver-steps)

```
sudo su -
apt update
apt -y upgrade
apt -y install linux-headers-$(uname -r) python3-venv software-properties-common
update-alternatives --install /usr/bin/python python /usr/bin/python3 1
curl -O https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/cuda-ubuntu2004.pin
mv cuda-ubuntu2004.pin /etc/apt/preferences.d/cuda-repository-pin-600
apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/7fa2af80.pub
add-apt-repository "deb https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/ /"
apt update
apt -y install cuda
exit
```

* EPC: Clone & Set up
```
git clone https://github.com/DavidSouther/EmergentPredictiveCoding.git
cd EmergentPredictiveCoding
python -m venv venv
source ./venv/bin/activate
pip install -r requirements.txt
```

* EPC: Run
```
./train_models.py
./halucinate_models.py
```
