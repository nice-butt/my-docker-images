FROM ubuntu:18.04
MAINTAINER Dr Victor Zheng (zwxne2010@gmail.com)

RUN apt-get -yqq update && apt-get install -yqq \
        curl sudo vim pkg-config zip g++ zlib1g-dev unzip python3 wget && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN useradd -lms /bin/bash -u 5000 -g sudo boss && \
    echo boss:boss | chpasswd && \
    groupadd boss && usermod -aG boss boss && \
    echo "boss ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers && \
    chmod 440 /etc/sudoers

USER boss
WORKDIR /tmp

#RUN curl -O https://github.com/bazelbuild/bazel/releases/download/1.0.1/bazel-1.0.1-installer-linux-x86_64.sh 
RUN wget https://github.com/bazelbuild/bazel/releases/download/1.0.1/bazel-1.0.1-installer-linux-x86_64.sh 

#RUN bash bazel-1.0.1-installer-linux-x86_64.sh -b

RUN chmod +x bazel-1.0.1-installer-linux-x86_64.sh && \
    ./bazel-1.0.1-installer-linux-x86_64.sh --user && \
    export PATH="$HOME/bin:$PATH"
