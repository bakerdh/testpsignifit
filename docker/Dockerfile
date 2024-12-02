FROM rocker/verse:4.4.2
ARG BUILDDIR="/tmp/build"
ARG PYTHON_VER="3.6.8"
WORKDIR ${BUILDDIR}

RUN apt-get update -qq && \
apt-get upgrade -y  > /dev/null 2>&1 && \
apt-get install wget gcc make zlib1g-dev -y -qq > /dev/null 2>&1 && \
wget --quiet https://www.python.org/ftp/python/${PYTHON_VER}/Python-${PYTHON_VER}.tgz > /dev/null 2>&1 && \
tar zxf Python-${PYTHON_VER}.tgz && \
cd Python-${PYTHON_VER} && \
./configure  > /dev/null 2>&1 && \
make > /dev/null 2>&1 && \
make install > /dev/null 2>&1 && \
rm -rf ${BUILDDIR} 


RUN apt-get update -qq
#RUN apt-get -y install cmake
#RUN apt-get -y --no-install-recommends install libglu1-mesa-dev
#RUN apt-get -y install libxml2-dev
#RUN apt-get -y install ghostscript
#RUN apt-get -y install libxt-dev
RUN apt-get -y install libssl-dev
RUN apt-get -y install git
#RUN apt-get -y install -y python3
#RUN apt-get -y install python3-pip
#RUN apt-get -y install python3-venv

RUN install2.r –error \
--deps TRUE \
rmarkdown \
reticulate \
knitr

#RUN R 'reticulate::use_python("/usr/bin/python3.9")'
