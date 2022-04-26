# euler-dde-arm64

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
    --name euler-dde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/euler-dde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it euler-dde-arm64 zsh
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

## euler-dde-arm64.toml

```toml
[main]
name = "euler"
tag = ["dde", "2022-04-26"]
os = "euler"
release = "dde"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "euler-dde_arm64_2022-04-26_03-38.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7eeeca056c9abdaa4f5ae61ce4cf6c761722d9dbd7259c6bf40392f691d3dc42"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4836731392

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1375707273

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220422"
previous_tag = "2022-04-22"
previous_file = "euler-dde_arm64_2022-04-22_01-59-rootfs.tar.zst"
previous_sha256 = "8f636ec543e827cdecda89377af3815aecb9b4dfba1c3eae99029da8319eb6b8"

current_version = "latest02"
current_date = "20220426"
old_file = "euler-dde_arm64_2022-04-22_08-16-rootfs.tar.zst"
old_sha256 = "43e4e5ff3d9e79a3c9da2f97d10249c2e32cb405eb6df0dffa025d4a0b4e47d6"
# edition 2021
# DISTRO_NAME=euler_arm64
# ROOTFS_FILE=euler-dde_arm64_2022-04-26_03-38-rootfs.tar.zst
# SHA256SUM=7eeeca056c9abdaa4f5ae61ce4cf6c761722d9dbd7259c6bf40392f691d3dc42
# BUILD_DATE=20220426
# BUILD_TAG=2022-04-26
# STATUS=completed
# VERSION=latest02
# END_TIME=03:38

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-26
begin = 2022-04-26 02:43:44.244640585+00:00
start-sync_0 = 03:18:22
start-zstd = 03:23:17
start-sync_1 = 03:36:47
end-sync_1 = 03:38:16
end = 2022-04-26 03:38:16.231405090+00:00

[server]
repo = "cake233/euler-dde-arm64"

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

[port]
tcp = [5902, 36080]
```
