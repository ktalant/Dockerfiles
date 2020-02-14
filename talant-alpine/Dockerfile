FROM alpine:latest
LABEL Talant Asan talant.py@gmail.com

RUN apk update && \
    apk add git && \
    apk add curl

ADD https://releases.hashicorp.com/terraform/0.12.20/terraform_0.12.20_linux_arm.zip .
RUN unzip terraform_0.12.20_linux_arm.zip && mv terraform /bin
