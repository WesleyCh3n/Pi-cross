FROM dockcross/base:latest

ARG GCC_VER
ARG PI_OS
ENV DEFAULT_DOCKCROSS_IMAGE wesleych3n/pi-cross:armv7-${PI_OS}-${GCC_VER}

ENV CROSS_TRIPLE arm-linux-gnueabihf
ENV XCC_PREFIX /usr/local
ENV CROSS_ROOT ${XCC_PREFIX}/${CROSS_TRIPLE}
ENV AS=${CROSS_ROOT}/bin/${CROSS_TRIPLE}-as \
    AR=${CROSS_ROOT}/bin/${CROSS_TRIPLE}-gcc-ar \
    CC=${CROSS_ROOT}/bin/${CROSS_TRIPLE}-gcc \
    CPP=${CROSS_ROOT}/bin/${CROSS_TRIPLE}-cpp \
    CXX=${CROSS_ROOT}/bin/${CROSS_TRIPLE}-g++ \
    LD=${CROSS_ROOT}/bin/${CROSS_TRIPLE}-ld \
    FC=${CROSS_ROOT}/bin/${CROSS_TRIPLE}-gfortran \
    RANLIB=${CROSS_ROOT}/bin/${CROSS_TRIPLE}-gcc-ranlib

ENV PKG_CONFIG_PATH /usr/lib/pkgconfig
ENV PATH ${CROSS_ROOT}/bin:$PATH
ENV LD_LIBRARY_PATH ${CROSS_ROOT}/lib:$LD_LIBRARY_PATH
ENV GCCPATH ${CROSS_ROOT}/libexec/gcc/${CROSS_TRIPLE}/${GCC_VER}
ENV ARFLAGS="--plugin $GCCPATH/liblto_plugin.so"
ENV RANLIBFLAGS="--plugin $GCCPATH/liblto_plugin.so"

COPY cross-pi-gcc-${GCC_VER}-2 ${CROSS_ROOT}
# Linux kernel cross compilation variables
ENV CROSS_COMPILE ${CROSS_TRIPLE}-
ENV ARCH arm
