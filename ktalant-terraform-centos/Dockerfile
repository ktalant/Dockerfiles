FROM centos:7
LABEL Talant Asan talant.py@gmail.com

RUN yum update -y && \
    yum install -y curl git wget unzip

ADD https://releases.hashicorp.com/terraform/0.12.20/terraform_0.12.20_linux_amd64.zip .
RUN unzip terraform_0.12.20_linux_amd64.zip && \
    mv terraform  /usr/local/bin
