# arch-kde-arm64

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
    --name arch-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-kde-arm64 zsh
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

## arch-kde-arm64.toml

```toml
[main]
name = "arch"
tag = ["kde", "2022-11-30"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-kde_arm64_2022-11-30_01-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "cfd322f7f62a2987fedc518a5de8cb5419eafa6a8a8815917bed2bacdb4cc24d"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.0G"
tar_bytes = 5357273600

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1522272703

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221123"
previous_tag = "2022-11-23"
previous_file = "arch-kde_arm64_2022-11-23_01-24-rootfs.tar.zst"
previous_sha256 = "ee4848a9f1b8bc03bb9fe5fd1820344a412a23964e591d3acb5099c39226d4e9"

current_version = "latest02"
current_date = "20221130"
old_file = "arch-kde_arm64_2022-11-20_21-22-rootfs.tar.zst"
old_sha256 = "9aebe3a494983bbc368995ffde714c338c6917c917ee4be51c86c811dc1943ad"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-kde_arm64_2022-11-30_01-18-rootfs.tar.zst
# SHA256SUM=cfd322f7f62a2987fedc518a5de8cb5419eafa6a8a8815917bed2bacdb4cc24d
# BUILD_DATE=20221130
# BUILD_TAG=2022-11-30
# STATUS=completed
# VERSION=latest02
# END_TIME=01:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-30
begin = 2022-11-30 00:33:18.452874116+00:00
start-sync_0 = 00:53:11
start-zstd = 00:58:53
start-sync_1 = 01:16:04
end-sync_1 = 01:18:01
end = 2022-11-30 01:18:01.303656141+00:00

[server]
repo = "cake233/arch-kde-arm64"

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
