FROM node:22

ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update
RUN apt-get -y upgrade
RUN npm install -g typescript-language-server
RUN npm install -g typescript
RUN npm install -g javascript-typescript-langserver
 
RUN mkdir /projects
RUN mkdir /modules

VOLUME /projects
VOLUME /modules

WORKDIR /projects
