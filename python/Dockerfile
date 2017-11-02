FROM ubuntu:xenial
ENV HOME /root
MAINTAINER kongminhao minhaokong@gmail.com
# try to install python2.7.7
RUN sed -i 's/archive.ubuntu.com/mirrors.ustc.edu.cn/g' /etc/apt/sources.list
RUN apt update -y &&  apt install  -y zlib1g-dev libbz2-dev libssl-dev libncurses5-dev  libsqlite3-dev libreadline-dev tk-dev libgdbm-dev libdb-dev libpcap-dev xz-utils libexpat-dev \
	&& apt-get install --no-install-recommends -y wget &&  rm -rf /var/lib/apt/lists/*
RUN set -ex \
	&& wget https://www.python.org/ftp/python/2.7.7/Python-2.7.7.tar.xz \
		| tar xz -C /tmp/ && cd /tmp/ \
		&& ./configure --prefix=/usr/local --enable-unicode=ucs4 --enable-shared LDFLAGS="-Wl,-rpath /usr/local/lib" \
		&& make && make install 
RUN set -ex \
	&& wget https://bootstrap.pypa.io/get-pip.py \
		&&	python2.7 get-pip.py 
