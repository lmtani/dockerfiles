FROM rocker/r-base:4.0.2

# Install dependencies
RUN apt-get update && apt-get install --no-install-recommends -y \
        git=1:2.27.0-1 \
        libcurl4-openssl-dev=7.68.0-1+b1 \
        libssl-dev=1.1.1g-1 \
        libxml2-dev=2.9.10+dfsg-5+b1 \
    && git clone --recursive https://github.com/rwdavies/STITCH.git \
    && mkdir STITCH/test-results STITCH/test-data \
    && ./STITCH/scripts/install-dependencies.sh \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Install STITCH release
WORKDIR /STITCH/releases
RUN wget https://github.com/rwdavies/stitch/releases/download/1.6.4/STITCH_1.6.4.tar.gz \
    && R CMD INSTALL STITCH_1.6.4.tar.gz
