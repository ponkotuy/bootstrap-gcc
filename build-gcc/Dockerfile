FROM gcc:9.4-buster

RUN apt update \
  && apt install -y libmpfr-dev libmpc-dev \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

WORKDIR /root
RUN wget http://ftp.tsukuba.wide.ad.jp/software/gcc/releases/gcc-11.2.0/gcc-11.2.0.tar.gz && tar xvf gcc-11.2.0.tar.gz && rm gcc-11.2.0.tar.gz

WORKDIR /root/gcc-11.2.0
RUN ./configure --disable-bootstrap --disable-multilib --enable-languages=c,c++
RUN make -j9
RUN ./host-x86_64-pc-linux-gnu/gcc/cpp --version
