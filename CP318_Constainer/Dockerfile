#Download base image ubuntu 16.04
FROM ubuntu:16.04

# Update Ubuntu Software repository
RUN apt-get -y update && apt-get -y --force-yes install vim \
build-essential    \
libgtk-3-dev       \
pkg-config         \
cython             \
git                \
libmysqlclient-dev \
libhdf5-dev        \
libxml2-dev        \
libxslt1-dev       \
openjdk-8-jdk      \
default-jre	      \
python-dev         \
python-pip         \
python-h5py        \
python-matplotlib  \
python-mysqldb     \
python-vigra       
RUN pip install --upgrade pip
RUN pip install --upgrade pillow
RUN pip install --upgrade pytest
RUN rm -rf CellProfiler
RUN git clone https://github.com/CellProfiler/CellProfiler.git
WORKDIR CellProfiler 
RUN pip install --ignore-installed --editable .
WORKDIR /
RUN git clone https://github.com/CellProfiler/CellProfiler-plugins.git
WORKDIR CellProfiler-plugins
RUN pip install --ignore-installed -r requirements.txt
RUN pip install docutils==0.10