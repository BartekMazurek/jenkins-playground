FROM jenkins/jenkins:lts

USER root

RUN apt-get update && apt-get install -y curl python3

RUN rm /usr/lib/python3.11/EXTERNALLY-MANAGED

RUN curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py && python3 get-pip.py

RUN pip3 install ansible

USER jenkins