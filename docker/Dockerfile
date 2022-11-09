FROM nvcr.io/nvidia/nvhpc:22.9-devel-cuda_multi-ubuntu20.04

RUN apt update && \
    DEBIAN_FRONTEND=noninteractive apt install -y python3 python3-pip python3-tk python3-dev python3-venv sudo 
# RUN apt update && \
#     DEBIAN_FRONTEND=noninteractive apt install -y build-essential gnupg cmake cmake-gui mesa-common-dev mesa-utils freeglut3-dev python3 python3-pip python3-tk python3-dev python3-venv git-core ninja-build git vim sudo wget unzip libglvnd-dev ffmpeg libsm6 libxext6 xvfb graphviz

# RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys A4B469963BF863CC

COPY ./requirements.txt /opt/requirements.txt
RUN pip3 install -r /opt/requirements.txt

RUN cd /tmp \
    && wget https://developer.download.nvidia.com/compute/mathdx/redist/mathdx/linux-x86_64/nvidia-mathdx-22.02.0-Linux.tar.gz \
    && tar xvf nvidia-mathdx-22.02.0-Linux.tar.gz \ 
    && rm -rf nvidia-mathdx-22.02.0-Linux.tar.gz \
    && mv nvidia-mathdx-22.02.0-Linux/opt/nvidia/mathdx /opt/nvidia/ \
    && rm -rf nvidia-mathdx-22.02.0-Linux

#RUN cd /opt \
#    && git clone https://gitlab-master.nvidia.com/mmacklin/warp.git \
#    && cd warp \
#    && python3 build_lib.py \
#    && pip3 install -e .


# ENV KAOLIN_INSTALL_EXPERIMENTAL=1
# ENV IGNORE_TORCH_VER=0
# # ENV TORCH_CUDA_ARCH_LIST="7.0 7.5"
# ENV CUB_HOME=/usr/local/cuda-*/include/
# RUN cd /tmp \
#     && git clone --recursive https://github.com/NVIDIAGameWorks/kaolin \
#     && cd kaolin \
#     && git checkout v0.11.0 \
#     && python3 setup.py develop




# RUN cd /tmp \
#     && git clone https://github.com/paulo-herrera/PyEVTK.git \
#     && cd PyEVTK/ \
#     && python3 setup.py install



# RUN DEBIAN_FRONTEND=noninteractive apt-get install -y libboost-iostreams-dev libtbb-dev libblosc-dev


#RUN cd /tmp \
#    && wget http://launchpadlibrarian.net/477178768/libtbb2_2020.2-2_amd64.deb \
#    && dpkg -i libtbb2_2020.2-2_amd64.deb
#ENV Tbb_INCLUDE_DIR="/usr/local/cuda-11.4/targets/x86_64-linux/include/thrust/system/tbb" 
#ENV Tbb_LIB_COMPONENTS="/usr/lib/x86_64-linux-gnu"
#ENV TBB_ROOT_DIR="/usr/local/cuda-11.4/targets/x86_64-linux/include/thrust/system/tbb"

#RUN cd /tmp \
#    && wget https://boostorg.jfrog.io/artifactory/main/release/1.80.0/source/boost_1_80_0.zip \
#    && unzip boost_1_80_0.zip \
#    && cd boost_1_80_0/ \
#    && ./bootstrap.sh --prefix=/usr/ \
#    && ./b2 \
#    && ./b2 install


#RUN cd /tmp \
#    && git clone https://github.com/Blosc/c-blosc.git \
#    && cd c-blosc \
#    && git checkout tags/v1.5.0 -b v1.5.0 \
#    && mkdir build \
#    && cd build \ 
#    && cmake .. \
#    && make -j4 \
#    && make install 
    
# RUN cd /tmp \
#     && git clone https://github.com/AcademySoftwareFoundation/openvdb.git \
#     && cd openvdb \
#     && git checkout fb09b35366ce851c146ad51296df02d99b811f06 \
#     && mkdir build \
#     && cd build \
#     && cmake .. \
#     && make -j4 \
#     && make install

# ENV PATH="${PATH}:/tmp/openvdb/nanovdb/:/tmp/openvdb/openvdb/"
# ENV LD_LIBRARY_PATH="${LD_LIBRARY_PATH}:/tmp/openvdb/nanovdb/:/tmp/openvdb/openvdb/"


# RUN cd /tmp \
#     && wget https://download.open-mpi.org/release/open-mpi/v4.1/openmpi-4.1.3.tar.gz \
#     && tar -xzf openmpi-4.1.3.tar.gz \
#     && cd openmpi-4.1.3 \
#     && ./configure --with-cuda --enable-install-libpmix \
#     && make -j4 install



# install nvshmem
# RUN apt update && \
#     DEBIAN_FRONTEND=noninteractive apt install -y libibverbs-dev librdmacm-dev autoconf

# COPY ./docker/nvshmem/nvshmem_src_2.6.0-1.txz /tmp/nvshmem_src_2.6.0-1.txz

# ENV CUDA_HOME=/usr/local/cuda
# ENV NVSHMEM_HOME=/usr/local/nvshmem
# ENV MPI_HOME=/usr/local/
# ENV HYDRA_HOME=/usr/local/hydra

# ENV NVSHMEM_MPI_SUPPORT=1 
# ENV NVSHMEM_USE_GDRCOPY=0 
# ENV MPICC=/usr/local/bin/mpicc
# ENV NVSHMEM_DEFAULT_PMIX=1
# #ENV NVSHMEM_PMIX_SUPPORT=1
# #ENV PMIX_HOME=/usr/local/bin/

# RUN ldconfig
# RUN cd /tmp \
#     && tar xvf nvshmem_src_2.6.0-1.txz \
#     && cd nvshmem_src_2.6.0-1 \
#     && make -j install \ 
#     && cd scripts \
#     && ./install_hydra.sh /tmp /usr/local/hydra


# ENV LD_LIBRARY_PATH="${LD_LIBRARY_PATH}:$CUDA_HOME/lib64:$MPI_HOME/lib:$NVSHMEM_HOME/lib"


# #ENV KAOLIN_INSTALL_EXPERIMENTAL=1
# #ENV IGNORE_TORCH_VER=0
# ## ENV TORCH_CUDA_ARCH_LIST="7.0 7.5"
# #ENV CUB_HOME=/usr/local/cuda/include/
# #RUN cd /tmp \
# #    && git clone --recursive https://github.com/NVIDIAGameWorks/kaolin \
# #    && cd kaolin \
# #    && git checkout v0.11.0 \
# #    && python3 setup.py develop
