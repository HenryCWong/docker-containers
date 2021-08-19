FROM debian:stable-slim

RUN mkdir -p /usr/share/man/man1 /usr/share/man/man2

RUN apt-get update && apt-get install -y --no-install-recommends curl git perl bzip2 gcc cpanminus \ 
    build-essential vim emacs openjdk-11-jre apt-transport-https ca-certificates gnupg lsb-release && \
    apt-get clean

RUN cpanm -v JSON
RUN cpanm -v Getopt::Long
RUN cpanm -v YAML::Tiny

RUN apt-get update

# For sorting, LC_ALL is C
ENV LC_ALL C
