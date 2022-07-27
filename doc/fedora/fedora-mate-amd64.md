# fedora-mate-amd64

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
    --name fedora-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-amd64 zsh
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

## fedora-mate-amd64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2022-07-27"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_amd64_2022-07-27_06-21.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "48d9d8134b2fd029b2157273163f0ddef00ffa5a26f81f521e0bb213a827698c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.7G"
tar_bytes = 4939410432

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1527555747

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220712"
previous_tag = "2022-07-12"
previous_file = "fedora-mate_amd64_2022-07-12_13-02-rootfs.tar.zst"
previous_sha256 = "ca9df518b155a49b7ef02ac88c203362067d753dd3d5241876307c86418b1e27"

current_version = "latest01"
current_date = "20220727"
old_file = "fedora-mate_amd64_2022-07-05_12-58-rootfs.tar.zst"
old_sha256 = "d8571a94e820c57ce4a8358b95e336ae2afd312aa9c5d8d54f4df2e93d0ca454"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-mate_amd64_2022-07-27_06-21-rootfs.tar.zst
# SHA256SUM=48d9d8134b2fd029b2157273163f0ddef00ffa5a26f81f521e0bb213a827698c
# BUILD_DATE=20220727
# BUILD_TAG=2022-07-27
# STATUS=completed
# VERSION=latest01
# END_TIME=06:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-27
begin = 2022-07-27 05:51:31.229709645+00:00
start-sync_0 = 05:57:20
start-zstd = 06:01:17
start-sync_1 = 06:19:55
end-sync_1 = 06:21:19
end = 2022-07-27 06:21:19.822079730+00:00

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
