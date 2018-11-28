FROM ubuntu:16.04

RUN apt update && \
    apt install -y wget git build-essential libz-dev gzip ca-certificates curl libbz2-dev liblzma-dev libncurses5-dev libncursesw5-dev zlib1g-dev python3 python3-pkg-resources autoconf libcurl4-gnutls-dev \
    && rm -rf /var/lib/apt/lists/*


# Install Htslib
RUN wget https://github.com/samtools/htslib/releases/download/1.9/htslib-1.9.tar.bz2 \
    && tar -jxvf htslib-1.9.tar.bz2 \
    && cd htslib-1.9/ \
    && ./configure --prefix=/usr/local \
    && make \
    && make install


ENV LD_LIBRARY_PATH=/usr/local/lib

# Setup ENV variables SAMTOOLS
ENV SAMTOOLS_BIN="samtools-1.9.tar.bz2" \
    SAMTOOLS_VERSION="1.9"

RUN wget https://github.com/samtools/samtools/releases/download/$SAMTOOLS_VERSION/$SAMTOOLS_BIN  \
  && tar -xf $SAMTOOLS_BIN \
  && mv /samtools-$SAMTOOLS_VERSION /samtools \
  && cd /samtools \
  && ./configure --enable-libcurl --with-htslib=/htslib-1.9 \
  && make \
  && make install

# Install crumble
RUN wget https://github.com/jkbonfield/crumble/releases/download/v0.8.1/crumble-0.8.1.tar.gz \
  && tar -xf crumble-0.8.1.tar.gz \
  && cd crumble-0.8.1 \
  && ./configure --with-htslib=/htslib-1.9 \
  && make \
  && make install
