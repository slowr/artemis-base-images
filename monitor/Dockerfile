FROM caida/bgpstream:2.2.0

LABEL maintainer="Dimitrios Mavrommatis <jim.mavrommatis@gmail.com>"

RUN apt-get update --allow-releaseinfo-change && \
    apt-get -y install build-essential python3-dev python3-setuptools

WORKDIR /root

RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/* /root/* && \
    ln -s /usr/bin/python3 /usr/local/bin/python

ENTRYPOINT ["bash"]
