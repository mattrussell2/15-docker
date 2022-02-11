FROM ubuntu:18.04

ARG utln

COPY . .

RUN apt-get update -y && apt-get upgrade              -y
RUN apt-get install lsb-release build-essential wget  -y
RUN apt-get install software-properties-common        -y
RUN apt-get install clang-format-10 valgrind ssh      -y 

RUN chmod +x ./install_clang
RUN bash ./install_clang 8
RUN ln -s /usr/bin/clang-8 /usr/bin/clang++
RUN ln -s /usr/bin/clang-format-10 /usr/bin/clang-format

RUN apt-get install ssh -y
RUN adduser --disabled-password --gecos "" ${utln} 
RUN usermod -aG sudo ${utln}
RUN echo -e "\nexport PS1=\"\\u@tufts-local:\\W\\$ \"" >> /home/${utln}/.bashrc
