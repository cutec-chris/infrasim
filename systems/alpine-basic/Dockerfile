from docker:dind
RUN apk update && apk add --no-cache \
      bash git py3-pip py3-jinja2 cmake 
RUN cd /tmp && git clone --depth=1 https://github.com/systemd/systemd
RUN echo "unicode=\"YES\"" >> /etc/rc.conf && \
    apk add --no-cache --virtual .build_deps \
        autoconf file g++ gcc libc-dev make pkgconf python3 ninja \
        util-linux pciutils usbutils coreutils binutils findutils grep \
        build-base gcc abuild binutils binutils-doc gcc-doc gperf libcap libcap-dev libbpf-dev libmount \
        valgrind-dev \
    && \
    pip3 install meson
RUN cd /tmp/systemd && \
    meson build && \
    ninja build