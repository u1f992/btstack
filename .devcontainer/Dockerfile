FROM ubuntu:24.04

RUN apt-get update && apt-get install --yes --no-install-recommends \
        build-essential \
        git \
        libusb-1.0-0-dev \
        make \
        mingw-w64 \
        pkg-config \
    && rm -rf /var/lib/apt/lists/*

# Create symlinks for case-insensitive Windows headers
# These headers use capital letters in source files which works on
# case-insensitive Windows filesystem but fails on Linux with MinGW cross-compiler
# - port/windows-winusb/main.c includes <Windows.h>
# - platform/windows/hci_transport_h2_winusb.c includes <SetupAPI.h>, <Winusb.h>
RUN ln -sf windows.h /usr/x86_64-w64-mingw32/include/Windows.h && \
    ln -sf setupapi.h /usr/x86_64-w64-mingw32/include/SetupAPI.h && \
    ln -sf winusb.h /usr/x86_64-w64-mingw32/include/Winusb.h

WORKDIR /workspace
