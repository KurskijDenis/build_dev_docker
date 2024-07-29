FROM golang:1.22

RUN apt-get -y update
RUN apt-get -y upgrade
RUN go install golang.org/x/tools/gopls@v0.16.0

RUN mkdir -p /go_pkg_volume
RUN mkdir -p /projects

ENV GOPATH=/go_pkg_volume
VOLUME /go_pkg_volume
VOLUME /projects

WORKDIR /projects
