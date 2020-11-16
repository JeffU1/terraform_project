FROM ubuntu:latest

RUN \
apt-get update -y && \
apt-get install unzip -y && \
apt-get install wget -y && \
apt-get install vim -y 

RUN wget https://releases.hashicorp.com/terraform/0.11.11/terraform_0.11.11_linux_amd64.zip
RUN unzip terraform_0.11.11_linux_amd64.zip
RUN mv terraform /usr/local/bin/
RUN terraform --version

RUN apt-get install -y python3-pip
RUN ln -s /usr/bin/python3 python
RUN pip3 install --upgrade pip
RUN python3 -V
RUN pip --version

RUN pip install awscli --upgrade --user

ENV PATH=~/.local/bin:$PATH
ADD . /usr/local/bin/templates
RUN mkdir ~/.aws && touch ~/.aws/credentials



