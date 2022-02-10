FROM ubuntu:18.04

COPY . .

RUN apt-get update -y 
RUN apt-get upgrade -y 
RUN apt-get install lsb-release          -y
RUN apt-get install build-essential      -y 

RUN chmod +x ./install_clang
RUN bash ./install_clang 8

RUN apt-get install clang-format         -y 
RUN apt-get install valgrind             -y 
RUN apt-get install ssh                  -y  
RUN ssh-keygen -b 2048 -t rsa -f ~/.ssh/id_rsa -q -N "" 
