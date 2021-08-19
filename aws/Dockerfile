FROM debian:stable-slim

RUN apt-get update && apt-get install -y --no-install-recommends curl vim ca-certificates unzip python3 python3-pip less

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && unzip awscliv2.zip && ./aws/install

RUN pip3 install boto3
