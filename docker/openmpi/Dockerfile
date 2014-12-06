#
# Docker Open MPI
# Related links:
#   http://techtinkering.com/2009/12/02/setting-up-a-beowulf-cluster-using-open-mpi-on-linux/

FROM ubuntu:14.04

RUN apt-get update
RUN apt-get -f install

#install OpenMPI
RUN sudo apt-get -y install openmpi-bin openmpi-common libopenmpi-dev openmpi-doc

RUN export LD_LIBRARY_PATH=/usr/lib/

# For slave nodes
RUN apt-get install -y openssh-server

# For client node
RUN apt-get install -y openssh-client
EXPOSE 22:22
EXPOSE 2049:2049
EXPOSE 2049:2049/udp
EXPOSE 111:111
EXPOSE 111:111/udp

RUN mkdir /openmpi
RUN mkdir /openmpi/ssh
ADD startSlave.sh /openmpi/
ADD startClient.sh /openmpi/
RUN chmod +x /openmpi/*.sh

#
RUN mkdir ~/.ssh
RUN ssh-keygen -t dsa -f ~/.ssh/id_dsa -N ''

#
RUN apt-get install -y nfs-kernel-server runit inotify-tools -qq
#RUN apt-get install -y nfs-kernel-server
RUN echo '/openmpi/ssh *(ro)' > /etc/exports