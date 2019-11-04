FROM ubuntu:18.04

MAINTAINER Dr Victor Zheng (zwxne2010@gmail.com)

RUN apt-get -yqq update && \
    apt-get -yqq install git \
        cmake \
        libilmbase-dev \
        zlibc \
        libboost-python-dev \
        libboost-thread-dev \
        python-dev \
        python-numpy

RUN apt-get -y install libboost-dev \
        libtbb-dev \
        libilmbase-dev \
        libopenexr-dev

RUN apt-get -yqq install g++-6 gcc-6 clang

RUN apt-get -yqq install liblog4cplus-dev \
    libglfw3-dev \
    doxygen

RUN git clone https://github.com/Blosc/c-blosc.git
RUN cd c-blosc && \
    git checkout tags/v1.5.0 -b v1.5.0 && \
    mkdir build && \
    cd build && \
    cmake .. && \
    make -j4 && \
    make install && \
    cd ../..

RUN apt-get install zlib1g-dev
RUN apt-get -yqq install libboost-iostreams-dev

RUN git clone https://github.com/AcademySoftwareFoundation/openvdb.git
RUN cd openvdb && \
    mkdir build && \
    cd build && \
    cmake .. && \
    make -j4 && \
    make install
