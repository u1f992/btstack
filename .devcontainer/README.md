## Setup

First, build and start the devcontainer:

```bash
devcontainer up --workspace-folder .
```

## Build

```bash
devcontainer exec --workspace-folder . bash -c "cd /workspaces/btstack && make -C port/libusb btkeyLib.so"

devcontainer exec --workspace-folder . bash -c "cd /workspaces/btstack && make -C port/windows-winusb btkeyLib.dll CC=x86_64-w64-mingw32-gcc"
```

## Clean

```bash
devcontainer exec --workspace-folder . bash -c "cd /workspaces/btstack && make -C port/libusb clean"

devcontainer exec --workspace-folder . bash -c "cd /workspaces/btstack && make -C port/windows-winusb clean"
```
