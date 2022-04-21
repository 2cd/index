# kali-xfce-arm64

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
    --name kali-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-arm64 zsh
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

## kali-xfce-arm64.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2022-04-21"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true
syntax_version = "0.0.0-alpha.3"

[file]
name = "kali-xfce_arm64_2022-04-21_13-43.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9e82b35ab00f530aa5ed2597842e1feaca5c9bc986f7b11e8f81ba67437d00c8"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.3G"
tar_bytes = 5624242688

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1603347944

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220414"
previous_tag = "2022-04-14"
previous_file = "kali-xfce_arm64_2022-04-14_13-35-rootfs.tar.zst"
previous_sha256 = "e7019593203dde0fb40133acd2c8fa6c50d2d589c743636e601e68fd057761de"

current_version = "latest01"
current_date = "20220421"
old_file = "kali-xfce_arm64_2022-04-07_18-55-rootfs.tar.zst"
old_sha256 = "17efe710241d89eb312cd80f007ade6cfd10600b22190c94235a39d43196abfd"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2022-04-21_13-43-rootfs.tar.zst
# SHA256SUM=9e82b35ab00f530aa5ed2597842e1feaca5c9bc986f7b11e8f81ba67437d00c8
# BUILD_DATE=20220421
# BUILD_TAG=2022-04-21
# STATUS=completed
# VERSION=latest01
# END_TIME=13:43

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-21
begin = 2022-04-21 12:23:49.578748695+00:00
start-sync_0 = 13:15:46
start-zstd = 13:21:22
start-sync_1 = 13:42:00
end-sync_1 = 13:43:41
end = 2022-04-21 13:43:41.774472505+00:00

[server]
repo = "cake233/kali-xfce-arm64"

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
