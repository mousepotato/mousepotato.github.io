---
layout: post
title: "如何在bluehost上安装SVN"
description: "本文介绍如何在bluehost空间上安装SVN版本控制软件。"
category: Technique
tags:
- Linux
---
{% include JB/setup %}

如何在bluehost上安装SVN


    ssh username@anotherbug.com 
    cd ~
    mkdir svn
    cd svn

    wget http://www.gtlib.gatech.edu/pub/apache/apr/apr-util-1.3.12.tar.gz
    wget http://www.gtlib.gatech.edu/pub/apache/apr/apr-1.4.5.tar.gz
    wget http://www.webdav.org/neon/neon-0.29.6.tar.gz
    wget http://subversion.tigris.org/downloads/subversion-1.6.17.tar.gz
    wget http://zlib.net/zlib-1.2.5.tar.gz

    tar –xzf *.tar.gz
    cd ~/svn/apr-1.4.5
    ./configure --prefix=$HOME LDFLAGS="-L/lib64"
    make
    make install

    cd ~/svn/apr-util-1.3.12
    ./configure --prefix=$HOME --with-apr=$HOME LDFLAGS="-L/lib64"
    make
    make install

    cd ~/svn/neon-0.29.6
    ./configure --enable-shared --prefix=$HOME LDFLAGS="-L/lib64"
    make
    make install

    cd zlib-1.2.5
    ./configure --prefix=$HOME
    make
    make install

    cd ~/svn/ subversion-1.6.17
    ./configure --prefix=$HOME --without-berkeley-db --with-zlib=$HOME --with-ssl LDFLAGS="-L/lib64"
    make
    make install
