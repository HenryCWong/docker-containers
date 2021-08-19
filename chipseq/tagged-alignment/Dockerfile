FROM debian:stable-slim

RUN mkdir -p /usr/share/man/man1 /usr/share/man/man2

RUN apt-get update && apt-get install -y --no-install-recommends curl git perl bzip2 gcc cpanminus \
    build-essential openjdk-11-jre && apt-get clean

RUN apt-get update && apt-get -y upgrade && apt-get install -y build-essential wget \
    libncurses5-dev zlib1g-dev libbz2-dev liblzma-dev libcurl3-dev && apt-get clean && apt-get purge

WORKDIR /usr/src/

RUN wget https://github.com/samtools/samtools/releases/download/1.12/samtools-1.12.tar.bz2 && \
    tar jxf samtools-1.12.tar.bz2 && \
    rm samtools-1.12.tar.bz2 && \	
    mv samtools-1.12 samtools && \
    cd samtools && \	
    ./configure --prefix $(pwd) && \
    make

RUN mv samtools/* /usr/local/bin
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/src/samtools
RUN apt-get install -y --no-install-recommends     apt-transport-https     ca-certificates     curl     gnupg     lsb-release
RUN apt-get update

RUN curl -L https://github.com/bwa-mem2/bwa-mem2/releases/download/v2.0pre2/bwa-mem2-2.0pre2_x64-linux.tar.bz2 | tar jxf - && mv bwa-mem2-2.0pre2_x64-linux/bwa-mem2* /usr/local/bin && rm -rf bwa*

RUN wget https://github.com/GregoryFaust/samblaster/releases/download/v.0.1.26/samblaster-v.0.1.26.tar.gz && \
    tar -zxf samblaster-v.0.1.26.tar.gz && mv samblaster-v.0.1.26 samblaster && cd samblaster && make
RUN  mv samblaster/* /usr/local/bin

ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/src/samtools:/usr/src/samblaster

# For sorting, LC_ALL is C
ENV LC_ALL C


