# jetsonclass
This repository contains code and instructions to support the Applied AI course using the Jetson Nano 2GB.

Follow the instructions at https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-2gb-devkit to prepare your Nano with the latest SD Image.

Pull the latest deep learning docker container:
sudo docker pull nvcr.io/nvidia/l4t-ml:r32.6.1-py3

Run the container by Executing the following:
sudo docker run --runtime nvidia -it --rm --network host \
    --volume ~/nvdli-data:/nvdli-nano/data \
    --device /dev/video0 \
nvcr.io/nvidia/l4t-ml:r32.6.1-py3
