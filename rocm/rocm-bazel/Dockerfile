FROM victordrz2019/base:bazel

MAINTAINER Dr Victor Zheng (zwxne2010@gmail.com)

#RUN useradd -lms /bin/bash -u 5000 -g sudo boss && \
#    echo boss:boss | chpasswd && \
#    groupadd boss && usermod -aG boss boss && \
#    echo "boss ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers && chmod 440 /etc/sudoers
USER boss


RUN sudo apt-get update && sudo apt-get dist-upgrade
RUN sudo apt-get -yqq install libnuma-dev
