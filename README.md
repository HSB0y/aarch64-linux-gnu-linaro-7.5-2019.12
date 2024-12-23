# Linaro GCC Builds for AArch64 (ARM64)

This repository hosts pre-built versions of **Linaro GCC** targeting the `aarch64-linux-gnu` architecture.

## About

This project compiles and packages **Linaro GCC 7.5-2019.12** for the ARM64 architecture.

### Build Details
- **Source Code**: [Linaro GCC 7.5 2019.12](https://releases.linaro.org/components/toolchain/gcc-linaro/7.5-2019.12/gcc-linaro-7.5-2019.12.tar.xz)
- **Version**: 7.5-2019.12
- **Target**: `aarch64-linux-gnu`

## Installation

Clone the repository:
   ```bash
   git clone https://github.com/HSB0y/aarch64-linux-gnu-linaro-7.5-2019.12.git
   cd aarch64-linux-gnu-linaro-7.5-2019.12
  ```
## Build from source code

To build the linaro gcc toolchain, follow the instructions below:

1. Download the source code
   ```bash
   wget https://releases.linaro.org/components/toolchain/gcc-linaro/7.5-2019.12/gcc-linaro-7.5-2019.12.tar.xz
   ```
3. Unzip the source code
   ```bash
   tar -xf gcc-linaro-7.5-2019.12.tar.xz
   ```
4. Change the working directory
   ```bash
   cd gcc-linaro-7.5-2019.12
   ```
5. Download dependencies
   ```bash
   ./contrib/download_prerequisites
   ```
6. Setup the build directory
   ```bash
   mkdir ../gcc-build
   cd ../gcc-build
   ```
7. Configure the build
   ```bash
   ../gcc-linaro-7.5.0-2019.12/configure \
    --prefix=<install-path> \
    --target=aarch64-linux-gnu \
    --enable-languages=c,c++ \
    --disable-multilib \
    --disable-nls \
    CC=gcc-11-aarch64-linux-gnu \
    CXX=g++-11-aarch64-linux-gnu
   ```
8. Build the toolchain
   ```bash
   make -j$(nproc)
   ```
9. Install the toolchain
    ```bash
    make install
    ```
