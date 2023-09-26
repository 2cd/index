# ubuntu-mate-amd64

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
    --name ubuntu-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-mate-amd64 zsh
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

## ubuntu-mate-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["mate", "2023-09-26", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-mate_amd64_2023-09-26_00-52.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "38f8303dd6a44f4f2b545b2fb83915649ad6c39351101a9594f633d585921bbb"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.2G"
tar_bytes = 4475235328

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1205156220

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230919"
previous_tag = "2023-09-19"
previous_file = "ubuntu-mate_amd64_2023-09-19_00-58-rootfs.tar.zst"
previous_sha256 = "8099d4a70d515c08e78d67eea421d99d05f284652f281e88ab046d70bbf820d7"

current_version = "latest01"
current_date = "20230926"
old_file = "ubuntu-mate_amd64_2023-09-12_00-58-rootfs.tar.zst"
old_sha256 = "8911aa18c60becde86e93142fe91249bb5cc413a6687228b089b89f933a44628"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-mate_amd64_2023-09-26_00-52-rootfs.tar.zst
# SHA256SUM=38f8303dd6a44f4f2b545b2fb83915649ad6c39351101a9594f633d585921bbb
# BUILD_DATE=20230926
# BUILD_TAG=2023-09-26
# STATUS=completed
# VERSION=latest01
# END_TIME=00:52

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-26
begin = 2023-09-26 00:26:07.452879541+00:00
start-sync_0 = 00:31:47
start-zstd = 00:35:30
start-sync_1 = 00:50:58
end-sync_1 = 00:52:49
end = 2023-09-26 00:52:49.614640677+00:00

[server]
repo = "cake233/ubuntu-mate-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu4) 2.38'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
