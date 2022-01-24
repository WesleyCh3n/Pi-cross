# Pi-cross

This is raspberry pi compiling toolchains (rpi compatible GCC version) in docker images based on [dockcross base image](https://github.com/dockcross/dockcross) and [rpi toolchains](https://github.com/abhiTronix/raspberry-pi-cross-compilers).

## 📦️ Usage

Usage is same as [dockcross](https://github.com/dockcross/dockcross#usage). Use `armv7-8.3.0` as example:

```bash
# create helper scripts
docker run --rm wesleych3n/pi-cross:armv7-8.3.0 > ./armv7-8.3.0

# grant execute mode
chmod +x ./armv7-8.3.0

# (Optional) put scripts into $PATH. Such as:
mv ./armv7-8.3.0 ~/.local/bin/

# into container shell
./armv7-8.3.0 bash

# (in container) verify compiler
$CC --version
# stdout:
#   arm-linux-gnueabihf-gcc (GCC) 8.3.0
#   Copyright (C) 2018 Free Software Foundation, Inc.
#   This is free software; see the source for copying conditions.  There is NO
#   warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
```

## 🔧 Configuration

Same as [dockcross](https://github.com/dockcross/dockcross#dockcross-configuration)

Most of the use case is docker run args (`--args|-a`).
*If args contain space, **quote** are required.*

For example, mount host path:

```bash
./armv7-8.3.0 -a "-v /path/to/mount:/container/path" bash
```

## 📎 Available Version

TODO

| Toolchains    | GCC versions |
| :-:           | :-:          |
| armv7(32-bit) | 8.3.0        |
| arm64(64-bit) | 8.3.0        |
