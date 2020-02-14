FROM debian:latest
LABEL Talant Asan talant.py@gmail

RUN apt update -y &&  apt upgrade -y\
    apt install -y wget git curl unzip

ADD https://releases.hashicorp.com/terraform/0.12.20/terraform_0.12.20_linux_amd64.zip .
RUN unzip terraform_0.12.20_linux_amd64.zip && \
    mv terraform /usr/local/bin

COPY ./config.txt  /usr/src/new_config.txt
