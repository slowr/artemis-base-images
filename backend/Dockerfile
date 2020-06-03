FROM mavromat/alpine-python:3.6

LABEL maintainer="Dimitrios Mavrommatis <jim.mavrommatis@gmail.com>"

RUN apk add --no-cache supervisor tcl postgresql-client postgresql-dev redis curl git libffi-dev cmake libssh

WORKDIR /root
# Install rtlib
RUN git clone -b v0.7.0 --depth 1 https://github.com/rtrlib/rtrlib.git && \
    cd rtrlib && \
    cmake -D CMAKE_BUILD_TYPE=Release . && \
    make -j 4 && make install && \
    ln -s /usr/local/lib64/librtr.so /usr/local/lib/librtr.so && \
    ln -s /usr/local/lib64/librtr.so.0 /usr/local/lib/librtr.so.0 && \
    ln -s /usr/local/lib64/librtr.so.0.7.0 /usr/local/lib/librtr.so.0.7.0 && \
    git clone https://github.com/rtrlib/python-binding.git && \
    cd python-binding && \
    git checkout 2ade90eddd1895515948481136c8197e9cada128 && \
    python setup.py build install