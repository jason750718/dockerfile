FROM ubuntu:latest

MAINTAINER jasonchang

USER root

RUN apt-get update && \
    apt-get install -y \
	build-essential \
	qtcreator \
	qt5-default \
	libqt5websockets5-dev \
	libqt5sql5-mysql \
	npm
	
RUN npm install pm2 -g
RUN pm2 install pm2-logrotate

RUN apt-get update && apt-get install -y openssh-server
RUN mkdir /var/run/sshd
RUN echo 'root:woer' | chpasswd
RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN sed -i 's/UsePAM yes/UsePAM no/' /etc/ssh/sshd_config
 
# SSH login fix. Otherwise user is kicked off after login
RUN sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd
 
ENV NOTVISIBLE "in users profile"
RUN echo "export VISIBLE=now" >> /etc/profile
 
EXPOSE 22 1236 8888
CMD ["/usr/sbin/sshd", "-D"]