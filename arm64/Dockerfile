FROM dockcross/base:latest

ENV DEFAULT_DOCKCROSS_IMAGE wesleych3n/pi-cross:arm64-8.3.0

ENV CROSS_TRIPLE aarch64-linux-gnu
ENV XCC_PREFIX /usr/local
ENV CROSS_ROOT ${XCC_PREFIX}/${CROSS_TRIPLE}
ENV AS=${CROSS_ROOT}/bin/${CROSS_TRIPLE}-as \
    AR=${CROSS_ROOT}/bin/${CROSS_TRIPLE}-gcc-ar \
    CC=${CROSS_ROOT}/bin/${CROSS_TRIPLE}-gcc \
    CPP=${CROSS_ROOT}/bin/${CROSS_TRIPLE}-cpp \
    CXX=${CROSS_ROOT}/bin/${CROSS_TRIPLE}-g++ \
    LD=${CROSS_ROOT}/bin/${CROSS_TRIPLE}-ld \
    FC=${CROSS_ROOT}/bin/${CROSS_TRIPLE}-gfortran \
    RANLIB=${CROSS_ROOT}/bin/${CROSS_TRIPLE}-ranlib

ENV PKG_CONFIG_PATH /usr/lib/pkgconfig
ENV PATH ${CROSS_ROOT}/bin:$PATH
ENV LD_LIBRARY_PATH ${CROSS_ROOT}/lib:$LD_LIBRARY_PATH
ENV GCCPATH ${CROSS_ROOT}/libexec/gcc/aarch64-linux-gnu/8.3.0
ENV ARFLAGS="--plugin $GCCPATH/liblto_plugin.so"
ENV RANLIBFLAGS="--plugin $GCCPATH/liblto_plugin.so"

COPY cross-pi-gcc-8.3.0-64 ${CROSS_ROOT}
# Linux kernel cross compilation variables
ENV CROSS_COMPILE ${CROSS_TRIPLE}-
ENV ARCH arm64
