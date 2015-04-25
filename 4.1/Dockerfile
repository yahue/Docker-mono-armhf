FROM armv7/armhf-ubuntu:14.10

MAINTAINER Lukas Novotny <lukas@dramiel.com>

# based on https://github.com/aspnet/aspnet-docker

# Get build dependencies, download/build/install mono 4.1.0
RUN apt-get update -qq \
    && apt-get install -qqy git autoconf libtool automake build-essential gettext unzip libgdiplus \
    && cd ~ \
    && git clone https://github.com/mono/mono.git \
    && cd mono \
    && git reset --hard 53dc56ee39a8e3b013231957aca4671b202c6410 \
    && ./autogen.sh --prefix="/usr/local" \
    && make get-monolite-latest \
    && make EXTERNAL_MCS="${PWD}/mcs/class/lib/monolite/basic.exe" -j4 \
    && make install \
    && cd .. \
    && rm mono -r

# Sync certificates from system
RUN mono cert-sync.exe /etc/ssl/certs/ca-certificates.crt