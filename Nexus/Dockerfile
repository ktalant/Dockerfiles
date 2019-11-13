FROM centos:7
LABEL maintainer=uchkunfan@gmail.com
RUN yum update -y && yum install wget -y \
    && yum install java-1.8.0-openjdk.x86_64 -y
RUN mkdir /app 
COPY . /app
WORKDIR /app
RUN wget https://download.sonatype.com/nexus/3/latest-unix.tar.gz
RUN tar -xvf nexus.tar.gz && mv nexus3* nexus
RUN adduser nexus
RUN sudo chown -R nexus:nexus /app/nexus
RUN sudo chown -R nexus:nexus /app/sonatype-work
COPY nexus.rc /app/nexus/bin/
COPY nexus.vmoptions  /app/nexus/bin/
COPY nexus.service /etc/systemd/system/nexus.service
RUN chkconfig nexus on && systemctl start nexus



