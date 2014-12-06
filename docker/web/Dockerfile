#
# Docker image Web app for MPI
#

# base image
FROM ubuntu:14.04


MAINTAINER DockerOpenMPI



# install dependencies
RUN apt-get -qq update
RUN apt-get install -y python python-pip

RUN ls -l

# install django packages
ADD req.txt /test/
RUN pip install -r test/req.txt
