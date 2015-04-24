FROM armv7/armhf-ubuntu:14.10

MAINTAINER Lukas Novotny <lukas@dramiel.com>

# based on dockerfile by Jo Shields <jo.shields@xamarin.com>
# based on dockerfile by Michael Friis <friism@gmail.com>

RUN apt-get update \
	&& apt-get install -y wget libgdiplus

RUN cd ~/ \
	&& wget https://www.dropbox.com/s/cluk56260rkqoi4/mono_3.12-1_armhf.deb?dl=1 \
	&& dpkg -i mono_3.12-1_armhf.deb?dl=1