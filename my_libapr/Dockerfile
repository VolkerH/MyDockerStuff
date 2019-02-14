FROM debian:latest
MAINTAINER Beaker

WORKDIR /srv

RUN apt-get update && apt-get install -y  \
  build-essential \
  git \
  wget \
  libhdf5-dev \
  libtiff5-dev \
  libblosc-dev \
  googletest \
  python3 \
  python3-dev

RUN echo "XXXXXXXXXXXXXXXXXXXXXXXXXXXXX"
RUN apt-get -y --fix-missing install  \
vim                \
cython             \
git                \
libhdf5-dev        \
libxml2-dev        \
libxslt1-dev       \
openjdk-8-jdk      \
default-jre	      \
python3-dev         \
python3-pip         \
python3-h5py        \
python3-matplotlib  \
python3-scipy       \
python-numpy       

RUN pip3 install tqdm
ADD installation_script.sh .
RUN chmod 777 installation_script.sh && ./installation_script.sh

ENTRYPOINT bash