FROM ubuntu:latest

MAINTAINER jasonchang

USER root

RUN apt-get update && \
    apt-get install -y \
	build-essential \
	qtcreator \
	qt5-default \
	libqt5websockets5-dev \
	libqt5sql5-mysql

EXPOSE 1236 8888