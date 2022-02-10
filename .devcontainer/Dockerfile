FROM ubuntu:18.04

RUN apt-get update -y && apt-get upgrade -y && \
    apt-get install build-essential      -y && \
    apt-get install ssh                  -y && \
    apt-get install clang-10             -y && \
    apt-get install valgrind             -y && \
    ssh-keygen -b 2048 -t rsa -f ~/.ssh/id_rsa -q -N "" 
