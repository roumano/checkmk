FROM ubuntu:18.04

SHELL ["/bin/bash", "-c"]
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get install -y \
    apache2 \
    apache2-dev \
    autoconf \
    build-essential \
    cmake \
    devscripts \
    dnsutils \
    dpatch \
    flex \
    gettext \
    git-buildpackage \
    libboost-all-dev \
    libcurl4-openssl-dev \
    libevent-dev \
    libffi-dev \
    libfreeradius-dev \
    libgd-dev \
    libglib2.0-dev \
    libgnutls28-dev \
    libgsf-1-dev \
    libkrb5-dev \
    libldap2-dev \
    libltdl-dev \
    libmcrypt-dev \
    libmysqlclient-dev \
    libncurses5-dev \
    libpango1.0-dev \
    libpcap-dev \
    libperl-dev \
    libpq-dev \
    libreadline-dev \
    librrd-dev \
    libsqlite3-dev \
    libssl-dev \
    libtool \
    libxml2-dev \
    openssh-client \
    patch \
    rpcbind \
    rsync \
    smbclient \
    texinfo \
    tk-dev \
    uuid-dev \
    && rm -rf /var/lib/apt/lists/*

# For the common part, split later
#RUN pip install pathlib2 \
#    typing

#RUN apt-get update \
#    && apt-get install -y \
#    rpm \
#    alien \
#    mono-xbuild \
#    && rm -rf /var/lib/apt/lists/*

COPY bw-build-gnu-toolchain.sh /usr/sbin
RUN bw-build-gnu-toolchain.sh -b

RUN mv /usr/bin/gcc /usr/bin/gcc-old || true \
    && mv /usr/bin/cc /usr/bin/cc-old || true \
    && ln -s /usr/bin/gcc-8 /usr/bin/gcc \
    && ln -s /usr/bin/gcc-8 /usr/bin/cc