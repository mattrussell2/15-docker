FROM ubuntu:18.04

RUN apt-get update -y && apt-get upgrade -y && \
    apt-get install build-essential      -y && \
    bash /workspaces/cs-15/.devcontainer/install_clang 8 && \
    apt-get install clang-format         -y && \
    apt-get install valgrind             -y && \
    apt-get install ssh                  -y && \ 
    ssh-keygen -b 2048 -t rsa -f ~/.ssh/id_rsa -q -N "" 
