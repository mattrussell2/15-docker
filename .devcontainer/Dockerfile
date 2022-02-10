FROM ubuntu:18.04

COPY . .

RUN apt-get update -y && apt-get upgrade              -y
RUN apt-get install lsb-release build-essential wget  -y
RUN apt-get install software-properties-common        -y
RUN apt-get install clang-format valgrind ssh         -y 

RUN chmod +x ./install_clang
RUN bash ./install_clang 8

RUN ssh-keygen -b 2048 -t rsa -f ~/.ssh/id_rsa -q -N "" 
