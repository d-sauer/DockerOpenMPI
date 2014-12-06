#
# Docker Open MPI
#
FROM ubuntu:14.04

#prepare folder
RUN mkdir openmpi
RUN cd openmpi

#install wget
RUN apt-get update
RUN apt-get -f install
RUN apt-get -y install wget

#download OpenMPI
RUN wget https://www.open-mpi.org/software/ompi/v1.8/downloads/openmpi-1.8.1.tar.gz

RUN apt-get -y install libibnetdisc-dev