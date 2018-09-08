#Download base image ubuntu 16.04
FROM ubuntu:16.04

# Update Ubuntu Software repository
RUN apt-get -y update 
RUN apt-get -y --force-yes install vim
RUN apt-get -y --force-yes install \
build-essential    \
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
python-scipy       \
python-numpy       \
python-vigra       \
python-wxgtk3.0    \
python-zmq
RUN apt-get upgrade
RUN pip install --upgrade pillow
RUN rm -rf CellProfiler
RUN git clone https://github.com/CellProfiler/CellProfiler.git
WORKDIR CellProfiler 
RUN pip install --editable .
WORKDIR /
RUN git clone https://github.com/VolkerH/CellProfiler-plugins.git
WORKDIR CellProfiler-plugins
RUN pip install -r requirements.txt