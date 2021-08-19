FROM debian:stable-slim

RUN mkdir -p /usr/share/man/man1 /usr/share/man/man2

RUN apt-get update && apt-get install -y --no-install-recommends curl git openjdk-11-jre     perl bzip2 vim emacs apt-transport-https ca-certificates gnupg lsb-release && apt-get clean

RUN apt-get update

RUN mkdir /cromwell/
