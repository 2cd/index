# fedora-mate-amd64

## How to run it?

```shell
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
    --name fedora-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it fedora-mate-amd64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```shell
    startvnc
```

or

```shell
    startx11vnc
```

or

```shell
    novnc
```

Note:

If you want to use novnc, then open your browser, and type the address:

```
localhost:36081
```

If you want to use tiger/x11vnc, then open vnc viewer, then type the address:

```
localhost:5903
```

## fedora-mate-amd64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2021-12-14"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "fedora-mate_amd64_2021-12-14_13-26.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "76b3219a98b82075ca39d525aea7c0708f8dcea2269fe525d06870a191111015"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4755871232

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1473802204

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211207"
previous_tag = "2021-12-07"
previous_file = "fedora-mate_amd64_2021-12-07_13-05-rootfs.tar.zst"
previous_sha256 = "4662759aaef419697e5f1fdbcb7838f4256f38b4d4fd1087542d863848b47924"

current_version = "latest01"
current_date = "20211214"
old_file = "fedora-mate_amd64_2021-11-30_15-53-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-mate_amd64_2021-12-14_13-26-rootfs.tar.zst
# SHA256SUM=76b3219a98b82075ca39d525aea7c0708f8dcea2269fe525d06870a191111015
# BUILD_DATE=20211214
# BUILD_TAG=2021-12-14
# STATUS=completed
# VERSION=latest01
# END_TIME=13:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-14
begin = 2021-12-14 13:02:37.837958974+00:00
start-sync_0 = 13:08:34
start-zstd = 13:12:49
start-sync_1 = 13:24:55
end-sync_1 = 13:26:23
end = 2021-12-14 13:26:24.007747944+00:00

[server]
repo = "cake233/fedora-mate-amd64"

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
