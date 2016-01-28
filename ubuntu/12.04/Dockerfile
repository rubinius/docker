FROM ubuntu:12.04

RUN apt-get update && apt-get install -y         bzip2         libyaml-0-2         libssl1.0.0

ADD https://rubinius-binaries-rubinius-com.s3-us-west-2.amazonaws.com/ubuntu/12.04/x86_64/rubinius-3.14.tar.bz2 /tmp/rubinius.tar.bz2
RUN cd /opt && tar xvjf /tmp/rubinius.tar.bz2

ENV PATH /opt/rubinius/3.14/bin:/opt/rubinius/3.14/gems/bin:$PATH

CMD ["bash"]
