# jetsonclass
## This repository contains code and instructions to support the Applied AI course using the Jetson Nano 2GB.

Follow the instructions at https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-2gb-devkit to prepare your Nano with the latest SD Image.

### Make sure you connected to wifi. If using headless connection, check your IP by typing:

ifconfig

### If your Wifi is not enabled, type the following:

sudo apt update
sudo apt install network-manager
sudo service NetworkManager start

### If you need to configure wifi, use the following command:

sudo nmcli device wifi connect 'enterRouterName' password 'enterRouterPassword'

### Pull the latest deep learning docker container:

sudo docker pull nvcr.io/nvidia/l4t-ml:r32.6.1-py3

### Run the container by Executing the following (this is a container for in class exercises:

sudo docker run --runtime nvidia -it --rm --network host \\
    --volume ~/nvdli-data:/nvdli-nano/data \\
    --device /dev/video0 \\
nvcr.io/nvidia/l4t-ml:r32.6.1-py3

### This container is from the DLI Getting Started with Jetson
## Refer to the DLI Lab for instructions. Command with suggested tag is below:

sudo docker run --runtime nvidia -it --rm --network host \\
    --volume ~/nvdli-data:/nvdli-nano/data \\
    --device /dev/video0 \\
    nvcr.io/nvidia/dli/dli-nano-ai:v2.0.1-r32.6.1
    
### This container is from the DLI Video Analytics  with Jetson and Deepstream
## Refer to the DLI Lab for instructions. Command with suggested tag is below:

sudo docker run --runtime nvidia -it --rm --network host \\
    -v /tmp/.X11-unix/:/tmp/.X11-unix \\
    -v /tmp/argus_socket:/tmp/argus_socket \\
    -v ~/my_apps:/dli/task/my_apps \\
    --device /dev/video0 \\
    nvcr.io/nvidia/dli/dli-nano-deepstream:v2.0.0-DS6.0.1
