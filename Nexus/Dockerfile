FROM openjdk:7
LABEL maintainer=uchkunfan@gmail.com
RUN apt-get update -y 
EXPOSE 8081
RUN useradd -ms /bin/bash nexus
RUN mkdir /app 
RUN apt-get install -y systemd-sysv
COPY . /app
WORKDIR /app
RUN wget https://download.sonatype.com/nexus/3/latest-unix.tar.gz
RUN tar -xzvf latest-unix.tar.gz && mv nexus-3* nexus
RUN chown -R nexus:nexus /app/nexus
RUN chown -R nexus:nexus /app/sonatype-work
COPY nexus.rc /app/nexus/bin/
COPY nexus.vmoptions  /app/nexus/bin/
COPY nexus.service /etc/systemd/system/nexus.service
RUN chmod 0644 /etc/systemd/system/nexus.service
RUN systemctl enable nexus  && systemctl start nexus



