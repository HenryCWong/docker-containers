FROM debian:stable-slim

RUN mkdir -p /usr/share/man/man1 /usr/share/man/man2

RUN apt-get update && \
apt-get install -y --no-install-recommends curl git python3 python3-pip openjdk-11-jre bzip2 build-essential vim emacs jq \
  less apt-transport-https ca-certificates gnupg lsb-release unzip && apt-get clean

RUN apt-get update	

RUN pip3 install --upgrade pip
RUN pip3 install miniwdl
RUN pip3 install setuptools


RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && unzip awscliv2.zip && ./aws/install

