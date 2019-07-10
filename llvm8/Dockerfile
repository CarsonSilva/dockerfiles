FROM ubuntu:18.04

LABEL maintainer="zhujia <magicletters@qq.com>"

RUN apt update && apt dist-upgrade -y && apt install -y wget gnupg2 --no-install-recommends

RUN wget -O - http://apt.llvm.org/llvm-snapshot.gpg.key | apt-key add - \
 && echo "deb http://apt.llvm.org/bionic/ llvm-toolchain-bionic-8 main" >> /etc/apt/sources.list \
 && apt update \
 && apt install -y clang-8 lldb-8 lld-8 cmake --no-install-recommends\
 && apt-get clean \
 && update-alternatives --install /usr/bin/clang clang /usr/bin/clang-8 100 \
 && update-alternatives --install /usr/bin/clang++ clang++ /usr/bin/clang++-8 100

ENV CC clang
ENV CXX clang++
