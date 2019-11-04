FROM victordrz2019/base:bazel

MAINTAINER Dr Victor Zheng (zwxne2010@gmail.com)

#RUN useradd -lms /bin/bash -u 5000 -g sudo boss && \
#    echo boss:boss | chpasswd && \
#    groupadd boss && usermod -aG boss boss && \
#    echo "boss ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers && chmod 440 /etc/sudoers
USER boss

RUN sudo apt-get update && sudo apt-get dist-upgrade
RUN sudo apt-get -yqq install libnuma-dev

RUN wget -qO - http://repo.radeon.com/rocm/apt/debian/rocm.gpg.key | sudo apt-key add -
RUN echo 'deb [arch=amd64] http://repo.radeon.com/rocm/apt/debian/ xenial main' | sudo tee /etc/apt/sources.list.d/rocm.list

# install rocm-dkms meta-package
RUN sudo apt-get -yqq update && \
    sudo apt-get -yqq install rocm-dkms
