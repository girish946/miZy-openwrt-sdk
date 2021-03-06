# miZy-openwrt-sdk

[![Build Status](https://travis-ci.com/hyphop/miZy-openwrt-sdk.svg?branch=master)](https://travis-ci.com/hyphop/miZy-openwrt-sdk)

build openwrt packages for miZy


## Get Source and Prepare

    mkdir /tmp/zero_builder
    cd /tmp/zero_builder
    
    git clone https://github.com/hyphop/miZy-openwrt-sdk.git
    
    cd miZy-openwrt-sdk
    
    ./openwrt.sdk.download
    ./openwrt.sdk.prepare
    ./openwrt.sdk.feeds

## build

    ./openwrt.sdk.make

## Easy make - by one-line command

    wget http://raw.githubusercontent.com/hyphop/miZy-openwrt-sdk/master/make_it_easy -O- | sh -

## clean

    ./openwrt.sdk.clean

## deps

openwrt sdk require this packages

    bison make flex time ash bc python gettext
    ncurses-dev u-boot-tools squashfs-tools zlib1g-dev xsltproc
    bzip2 lzma lzop lbzip2 gawk xz-utils aufs-tools 
    subversion git mercurial

<!--
RUN apt-get update && apt-get install -y \
  build-essential \
  libncurses5-dev \
  gawk \
  git \
  subversion \
  libssl-dev \
  gettext \
  unzip \
  zlib1g-dev \
  file python \
  mercurial \
  flex \
  quilt \
  xsltproc \
  libxml-parser-perl \
  bzr \
  ecj \
  cvs \
  wget \
  b43-fwcutter
-->

## VM compilation 

compilation / cross-compilation its painfull process sometimes! 
try special prepared and tested VM 
with preinstalled all necessary packages https://github.com/hyphop/miZy-builder

	# working tested vm
	ver=jessie ./miZy_builder_vm_generate  yes  # debian jessie
	# or 
	ver=xenial ./miZy_builder_vm_generate  yes  # ubuntu xenial

	https://github.com/hyphop/miZy-builder/releases/download/vm1/miZyBldr.jessie.squashfs
	https://github.com/hyphop/miZy-builder/releases/download/vm1/miZyBldr.xenial.squashfs

<!--
    console=no password=1234 mem=3G ./miZy_builder_vm start
-->

## NOTE!

if building process failed try run make again, maybe problem will be solve

## output DIRs

    ./dl   - download src packages
    ./bin  - compiled packages

## custom feeds install

    ./openwrt/scripts/feeds install libgme

## custom package build

    ./openwrt.sdk.make package/libgme/configure
    ./openwrt.sdk.make package/libgme/install

## mizy-feeds

openwrt.sdk.feeds.list

* busybox-mizy
* fluidsynth
* libgme
* libmodplug
* markdown
* html2text
* sunxi-tools
* vorbis-tools
* mkexfat

## miZy 
 
miZy - open source minimalistic tiny fast embedded Linux system, (for sunxi Orange Pi Zero, another sunxi boards maybe work too )

## LINKS

- [https://hyphop.github.io/mizy/](https://hyphop.github.io/mizy/)
- [https://github.com/hyphop/miZy-linux-kernel](https://github.com/hyphop/miZy-linux-kernel)
- [https://github.com/hyphop/miZy-builder](https://github.com/hyphop/miZy-builder)
- [https://github.com/hyphop/miZy-uboot](https://github.com/hyphop/miZy-uboot)
