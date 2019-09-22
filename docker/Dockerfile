FROM debian:buster

WORKDIR /root/work

RUN apt-get update
RUN apt-get install -y wget
RUN apt-get install -y vim-nox
RUN apt-get install -y build-essential
RUN apt-get install -y libpcre3-dev
RUN apt-get install -y python
RUN wget https://github.com/danmar/cppcheck/archive/1.89.tar.gz
RUN tar xvf 1.89.tar.gz
WORKDIR cppcheck-1.89/
RUN make MATCHCOMPILER=yes FILESDIR=/usr/share/cppcheck HAVE_RULES=yes CXXFLAGS="-O2 -DNDEBUG -Wall -Wno-sign-compare -Wno-unused-function"
RUN make MATCHCOMPILER=yes FILESDIR=/usr/share/cppcheck HAVE_RULES=yes CXXFLAGS="-O2 -DNDEBUG -Wall -Wno-sign-compare -Wno-unused-function" install
WORKDIR ..
RUN rm -rf cppcheck-1.89
RUN rm -f 1.89.tar.gz

