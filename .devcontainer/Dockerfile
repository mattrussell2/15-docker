FROM ubuntu:22.04

ARG utln

COPY . build

RUN apt-get update -y && apt-get upgrade              -y
RUN apt-get install lsb-release build-essential wget  -y
RUN apt-get install software-properties-common git    -y
RUN apt-get install clang-format valgrind ssh sudo    -y 
RUN apt-get install time clang-12                     -y

# install python packages
RUN python3 -m pip install --upgrade pip
RUN python3 -m pip install toml dataclasses tqdm filelock python_dateutil

# use clang++
RUN ln -s /usr/bin/clang++-12 /usr/bin/clang++

RUN adduser --disabled-password --gecos "" ${utln} 
RUN usermod -aG sudo ${utln}

RUN printf "${utln}  ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
RUN printf "export PS1=\"\\u@tufts-local:\\W\\$ \"" >> /home/${utln}/.bashrc

# clone the course repository
#ARG REPO_REMOTE_PATH
#RUN cd /autograder/source/ && git clone $REPO_REMOTE_PATH course-repo
