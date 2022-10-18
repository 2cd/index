# fedora-kde-amd64

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
    --name fedora-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-kde-amd64 zsh
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

## fedora-kde-amd64.toml

```toml
[main]
name = "fedora"
tag = ["kde", "2022-10-18"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_amd64_2022-10-18_13-31.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8244e69b83c59fbd1ddac2840f28a44bafee8499a42144f7a1528aa60dced5a2"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.1G"
tar_bytes = 5378989568

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1753952942

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221011"
previous_tag = "2022-10-11"
previous_file = "fedora-kde_amd64_2022-10-11_13-34-rootfs.tar.zst"
previous_sha256 = "bd4ca2aca5c0ad1daf1a1e1596db99d40fd848d458f02576129e841ef44349ac"

current_version = "latest01"
current_date = "20221018"
old_file = "fedora-kde_amd64_2022-10-04_13-25-rootfs.tar.zst"
old_sha256 = "1d9c09e970ca4e8c4327ac7c4b6a62778831665486632daa7ca6c287aaf57083"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-kde_amd64_2022-10-18_13-31-rootfs.tar.zst
# SHA256SUM=8244e69b83c59fbd1ddac2840f28a44bafee8499a42144f7a1528aa60dced5a2
# BUILD_DATE=20221018
# BUILD_TAG=2022-10-18
# STATUS=completed
# VERSION=latest01
# END_TIME=13:31

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-18
begin = 2022-10-18 12:50:02.921812114+00:00
start-sync_0 = 13:00:15
start-zstd = 13:05:44
start-sync_1 = 13:29:39
end-sync_1 = 13:31:44
end = 2022-10-18 13:31:44.362803668+00:00

[server]
repo = "cake233/fedora-kde-amd64"

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
