FROM ubuntu:18.04

RUN apt update && \
    apt install -y build-essential wget && \
    rm -rf /var/lib/apt/lists/*

RUN wget ftp://ftp.expasy.org/databases/prosite/ps_scan/ps_scan_linux_x86_elf.tar.gz && \
    wget ftp://ftp.expasy.org/databases/prosite/prosite.dat && \
    tar -xf ps_scan_linux_x86_elf.tar.gz && \
    rm ps_scan_linux_x86_elf.tar.gz && \
    mv prosite.dat /ps_scan/

ENV PATH="/ps_scan:${PATH}"