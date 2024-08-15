# syntax=docker/dockerfile:1

FROM nvidia/cuda:12.1.0-devel-ubuntu22.04 as base

LABEL	author="Cheng Liang" \
	description="develop enviroment for TensorRT-LLM and Mixtral8x7B"

RUN apt-get update && apt-get -y install python3.10 python3-pip openmpi-bin libopenmpi-dev git git-lfs
RUN pip3 install tensorrt_llm -U --extra-index-url https://pypi.nvidia.com
RUN git clone https://github.com/NVIDIA/TensorRT-LLM.git
RUN pip3 install -r TensorRT-LLM/examples/mixtral/requirements.txt
RUN git lfs install

# Run image with docker run --rm --ipc=host --runtime=nvidia --gpus all --entrypoint /bin/bash -it [image]
