FROM ubuntu:15.10

RUN locale-gen en_US.UTF-8
RUN dpkg-reconfigure locales

ENV LANG en_US.UTF-8
ENV LC_ALL en_US.UTF-8
ENV PATH /opt/rubinius/bin:/opt/rubinius/gems/bin:$PATH

RUN apt-get -y update && \
    apt-get -y install build-essential \
                       bison \
                       llvm-3.5 llvm-3.5-dev \
                       ruby ruby-dev rake \
                       wget \
                       libedit-dev \
                       libeditline-dev \
                       libncurses5-dev \
                       libreadline-dev \
                       libssl-dev \
                       libyaml-dev \
                       zlib1g-dev

RUN gem install bundler

RUN wget http://releases.rubinius.com/rubinius-3.0.tar.bz2 \
         -O /tmp/rubinius.tar.bz2

RUN cd /tmp && tar jxf rubinius.tar.bz2 && rm *.tar.bz2 && cd rubinius-* && \
    bundle install && \
    ./configure --prefix=/opt/rubinius \
                --llvm-config=/usr/bin/llvm-config-3.5 && \
    rake build && \
    rake install && \
    cd /tmp && rm -rf rubinius-*

RUN apt-get clean
