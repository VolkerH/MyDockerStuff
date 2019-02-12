FROM debian:latest
MAINTAINER Volker Hilsenstein

WORKDIR /
RUN apt-get update
RUN apt-get install tar 
RUN apt-get install bzip2
RUN apt-get install libgomp1
ADD https://github.com/SuperElastix/elastix/releases/download/4.9.0/elastix-4.9.0-linux.tar.bz2 /
RUN tar xvjf /elastix-4.9.0-linux.tar.bz2



