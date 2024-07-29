FROM ubuntu:24.04

ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update
RUN apt-get -y upgrade
RUN apt-get -y install \
    libllvm-17-ocaml-dev libllvm17 llvm-17 llvm-17-dev llvm-17-doc llvm-17-examples llvm-17-runtime \
    clang-17 clang-tools-17 clang-17-doc libclang-common-17-dev libclang-17-dev libclang1-17 clang-format-17 python3-clang-17 clangd-17 clang-tidy-17 \
    libclang-rt-17-dev \
    libpolly-17-dev \
    lldb-17 \
    lld-17 \
    libc++-17-dev libc++abi-17-dev \
    libomp-17-dev \
    libclc-17-dev \
    libunwind-17-dev \
    libmlir-17-dev mlir-17-tools \
    flang-17 \
    libclang-rt-17-dev-wasm32 libclang-rt-17-dev-wasm64 libc++-17-dev-wasm32 libc++abi-17-dev-wasm32 libclang-rt-17-dev-wasm32 libclang-rt-17-dev-wasm64

RUN apt-get -y install cmake python3-pip
RUN pip install cmake-language-server --break-system-packages
RUN apt-get -y install ccls

RUN mkdir /projects
RUN mkdir /thirdparty

VOLUME /projects
VOLUME /thirdparty

WORKDIR /projects
