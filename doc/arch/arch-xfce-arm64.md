# arch-xfce-arm64

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
    --name arch-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-arm64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```sh
    startvnc
```

or

```
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

## arch-xfce-arm64.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2022-11-09"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_arm64_2022-11-09_00-50.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ff5d7fe53fb70da568ce7797cd1ba4b456ee2f64ccd1067d0f2192cd4b8fe610"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4360807936

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1271054461

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221102"
previous_tag = "2022-11-02"
previous_file = "arch-xfce_arm64_2022-11-02_00-51-rootfs.tar.zst"
previous_sha256 = "86bf06595bfaeac9157aff6a1cd33f30bc46f977f5d70313643a20620814be1d"

current_version = "latest02"
current_date = "20221109"
old_file = "arch-xfce_arm64_2022-10-26_01-13-rootfs.tar.zst"
old_sha256 = "3b4452a697ac58b67d513454b52a83bdc34860a4e619f6c6da5ff40ae1eb4e0b"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-xfce_arm64_2022-11-09_00-50-rootfs.tar.zst
# SHA256SUM=ff5d7fe53fb70da568ce7797cd1ba4b456ee2f64ccd1067d0f2192cd4b8fe610
# BUILD_DATE=20221109
# BUILD_TAG=2022-11-09
# STATUS=completed
# VERSION=latest02
# END_TIME=00:50

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-09
begin = 2022-11-09 00:09:11.908596164+00:00
start-sync_0 = 00:27:07
start-zstd = 00:31:29
start-sync_1 = 00:49:09
end-sync_1 = 00:50:35
end = 2022-11-09 00:50:35.687282948+00:00

[server]
repo = "cake233/arch-xfce-arm64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = true
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = true
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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
