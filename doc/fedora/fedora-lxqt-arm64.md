# fedora-lxqt-arm64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
    apt install qemu-user-static
fi

# 5903 is the host vnc port
# 5902 is the container vnc port
# 36080 is the container novnc port
docker run \
    -it \
    --shm-size 512m \
    -p 5903:5902 \
    -p 36081:36080 \
    --name fedora-lxqt-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-lxqt-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-lxqt-arm64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```sh
    startvnc
```

or

```sh
    startx11vnc
```

or

```sh
    novnc
```

Note:

If you want to use novnc, then open your browser, and type the address:

```
http://localhost:36081
```

If you want to use tiger/x11vnc, then open vnc viewer, then type the address:

```
localhost:5903
```

## fedora-lxqt-arm64.toml

```toml
[main]
name = "fedora"
tag = ["lxqt", "2022-01-11"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "fedora-lxqt_arm64_2022-01-11_13-46.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "b06acbd5ca4585969582b8e312c0e22d9049f8d067a41a6cbc81571bb73e8476"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.4G"
tar_bytes = 4664733184

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "976M"
zstd_bytes = 1022898073

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211102"
previous_tag = ""
previous_file = "fedora-rawhide_arm64+lxqt-2021_11-02-rootfs.tar.zst"
previous_sha256 = "3148521c15bba60de747c6f5fbfdbf3f1591601ec23bd53a319bd3d8a3cd444e"

current_version = "latest02"
current_date = "20220111"
old_file = "fedora-rawhide_arm64+lxqt-2021_10-26-rootfs.tar.zst"
old_sha256 = "3e47a4fc80dd5ee4013b9db146ae5c2c5713ea0884d27d3d45508ac9c3127ab3"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-lxqt_arm64_2022-01-11_13-46-rootfs.tar.zst
# SHA256SUM=b06acbd5ca4585969582b8e312c0e22d9049f8d067a41a6cbc81571bb73e8476
# BUILD_DATE=20220111
# BUILD_TAG=2022-01-11
# STATUS=completed
# VERSION=latest02
# END_TIME=13:46

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-11
begin = 2022-01-11 12:45:27.020514095+00:00
start-sync_0 = 13:30:48
start-zstd = 13:34:20
start-sync_1 = 13:45:30
end-sync_1 = 13:46:32
end = 2022-01-11 13:46:32.323957427+00:00

[server]
repo = "cake233/fedora-lxqt-arm64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
previous = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (GNU libc) 2.34.9000'
zsh = 'zsh 5.8 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
