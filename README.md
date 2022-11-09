## HPC SDK Starter
This docker container will provide the NVIDIA HPC SDK 22.9 release; find the documentation at https://docs.nvidia.com/hpc-sdk/index.html

To get an idea of what you could do watch the GTC 2022 video at https://www.nvidia.com/en-us/on-demand/session/gtcfall22-a41087/


Moreover, this will also come with the latest version of NVIDIA WARP; Google JAX; and MathDX (containing cuFFTDx).

## Getting Started

To build the docker image run `./launch build` from the parent directory, then you can run the development environment by `./launch dev` 
which also starts a shell in the running container. Alternatively, you can run the container in the daemon mode in the backgroun by `./launch dev -d`

If the container is running in the background (check if `hpc_sdk` is running by `docker ps` in your terminal) you can attach to the running container by `./launch attach`
