FROM openjdk:7
LABEL maintainer=uchkunfan@gmail.com
RUN apt-get update -y 
EXPOSE 8081
RUN mkdir /app 
COPY . /app
WORKDIR /app
RUN wget https://download.sonatype.com/nexus/3/latest-unix.tar.gz
RUN tar -xzvf latest-unix.tar.gz && mv nexus-3* nexus
RUN adduser nexus
RUN chown -R nexus:nexus /app/nexus
RUN chown -R nexus:nexus /app/sonatype-work
COPY nexus.rc /app/nexus/bin/
COPY nexus.vmoptions  /app/nexus/bin/
COPY nexus.service /etc/systemd/system/nexus.service
RUN chkconfig nexus on && systemctl start nexus



