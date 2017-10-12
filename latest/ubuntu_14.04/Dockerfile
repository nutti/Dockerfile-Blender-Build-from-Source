FROM ubuntu:14.04

RUN apt-get update -y
RUN apt-get install -y git
RUN apt-get install -y build-essential
RUN apt-get install -y cmake cmake-curses-gui

WORKDIR /root
RUN mkdir blender
RUN git clone https://git.blender.org/blender.git

WORKDIR /root/blender/blender
RUN git submodule update --init --recursive
RUN git submodule foreach git checkout master
RUN git submodule foreach git pull --rebase origin master

RUN ./build_files/build_environment/install_deps.sh

RUN make

