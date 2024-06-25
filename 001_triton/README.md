# Triton lecture

This lecture is adapted from [CUDA MODE](https://github.com/insop/cuda-mode-lectures/tree/main/lecture_014), with the blend of AMD GPU acceleration.

## Environment Setup
To setup the environment:
1. Following Link: [Install PyTorch for ROCm — Use ROCm on Radeon GPUs​](https://rocm.docs.amd.com/projects/radeon/en/latest/docs/install/native_linux/install-pytorch.html)
    ```bash
    
    sudo docker pull rocm/pytorch:rocm6.1.3_ubuntu22.04_py3.10_pytorch_release-2.1.2​
    sudo docker run -it \​
      --cap-add=SYS_PTRACE \​
      --security-opt seccomp=unconfined \​
      --device=/dev/kfd \​
      --device=/dev/dri \​
      --group-add video \​
      --ipc=host \​
      --shm-size 8G \​
      -p 8888:8888 \
      rocm/pytorch:rocm6.1.3_ubuntu22.04_py3.10_pytorch_release-2.1.2
    ```

2. Install dependencies.
   - Install Rust from https://www.rust-lang.org/tools/install
      ```bash
      curl https://sh.rustup.rs -sSf | sh
      source ~/.cargo/env
      ```
   - Install python dependencies:
     ```bash
     pip install matplotlib pandas numpy==1.26.4 notebook
     ```

3. Clone [Triton](https://github.com/ROCm/triton.git ) from ROCm Github. Github: https://github.com/ROCm/triton.git ​
    ```bash
    pip uninstall triton​
    git clone https://github.com/ROCm/triton.git
    cd triton/python​
    pip install ninja cmake wheel
    pip install .
    ```
4. Launch Notebook
   ```bash
   jupyter notebook
   ```
