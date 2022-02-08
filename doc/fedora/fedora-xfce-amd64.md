# fedora-xfce-amd64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not amd64, then install qemu & binfmt-support.
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
    --name fedora-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-xfce-amd64 zsh
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

## fedora-xfce-amd64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2022-02-08"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "fedora-xfce_amd64_2022-02-08_13-26.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "9ac800649bd151860a9099d7ba4f944e0eba2e3074938397203d373910534695"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3823429120

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1258082666

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220201"
previous_tag = "2022-02-01"
previous_file = "fedora-xfce_amd64_2022-02-01_13-07-rootfs.tar.zst"
previous_sha256 = "dbdb82ae015858faaaba05d51e6316c56aaa7da7821e3d1e093a45425d9e36f7"

current_version = "latest02"
current_date = "20220208"
old_file = "fedora-xfce_amd64_2022-01-25_13-13-rootfs.tar.zst"
old_sha256 = "45760148ae81d8daf57dc8c1ded1cf373685b98d3f73724c7e6c208142a62213"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-xfce_amd64_2022-02-08_13-26-rootfs.tar.zst
# SHA256SUM=9ac800649bd151860a9099d7ba4f944e0eba2e3074938397203d373910534695
# BUILD_DATE=20220208
# BUILD_TAG=2022-02-08
# STATUS=completed
# VERSION=latest02
# END_TIME=13:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-08
begin = 2022-02-08 13:03:30.718521429+00:00
start-sync_0 = 13:10:20
start-zstd = 13:14:47
start-sync_1 = 13:25:35
end-sync_1 = 13:26:56
end = 2022-02-08 13:26:56.921106852+00:00

[server]
repo = "cake233/fedora-xfce-amd64"

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
zsh = 'zsh 5.8 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
