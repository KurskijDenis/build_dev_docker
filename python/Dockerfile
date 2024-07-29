FROM python:3.12

ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get -y update
RUN apt-get -y upgrade
# in order to install bin files in the target dir we need to upgrade pip 
RUN pip install --upgrade pip

# you can install pkg by pip in this dir and 
# pylsp will see these pkgs if you mount it in .lsp-docker.yaml 
# pip install -t /python_pkg_volume requests
RUN mkdir /python_pkg_volume
RUN mkdir /projects

ENV PATH=/python_pkg_volume/bin:$PATH
ENV PYTHONPATH=/python_pkg_volume:$PYTHONPATH

VOLUME /python_pkg_volume
VOLUME /projects

WORKDIR /projects
