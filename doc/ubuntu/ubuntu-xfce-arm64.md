# ubuntu-xfce-arm64

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
    --name ubuntu-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-xfce-arm64 zsh
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

## ubuntu-xfce-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2022-04-26", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_arm64_2022-04-26_01-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8096b8b11b4782f5b8f69c5f64d98075d5cfb01ae445379d0486dc1660af41e3"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.3G"
tar_bytes = 3461129728

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "914M"
zstd_bytes = 958095976

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220419"
previous_tag = "2022-04-19"
previous_file = "ubuntu-xfce_arm64_2022-04-19_01-23-rootfs.tar.zst"
previous_sha256 = "85fa8638ac3c3db1bf378d23c100018e9c9a934e7e79f5845bf1f7c5bb596807"

current_version = "latest02"
current_date = "20220426"
old_file = "ubuntu-xfce_arm64_2022-04-12_00-10-rootfs.tar.zst"
old_sha256 = "3f09222ae28d2aa9ea1fbae822f2486686a3bc7dc3564cb4695929e407274991"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-xfce_arm64_2022-04-26_01-08-rootfs.tar.zst
# SHA256SUM=8096b8b11b4782f5b8f69c5f64d98075d5cfb01ae445379d0486dc1660af41e3
# BUILD_DATE=20220426
# BUILD_TAG=2022-04-26
# STATUS=completed
# VERSION=latest02
# END_TIME=01:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-26
begin = 2022-04-26 00:21:10.652846846+00:00
start-sync_0 = 00:50:59
start-zstd = 00:53:51
start-sync_1 = 01:07:47
end-sync_1 = 01:08:50
end = 2022-04-26 01:08:50.788897906+00:00

[server]
repo = "cake233/ubuntu-xfce-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
