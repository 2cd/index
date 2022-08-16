# euler-dde-amd64

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
    --name euler-dde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/euler-dde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it euler-dde-amd64 zsh
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

## euler-dde-amd64.toml

```toml
[main]
name = "euler"
tag = ["dde", "2022-08-16"]
os = "euler"
release = "dde"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "euler-dde_amd64_2022-08-16_03-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "34298ef91c75addf39b0b50b81ceaafb5024e49ed63393c9ee26e2dff3a77ce6"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4840218112

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1422699203

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220615"
previous_tag = "2022-06-15"
previous_file = "euler-dde_amd64_2022-06-15_00-38-rootfs.tar.zst"
previous_sha256 = "61199add278022cf630fcdb68c70f13c9260bd48a50760885a50acd2fee9e9c8"

current_version = "latest02"
current_date = "20220816"
old_file = "euler-dde_amd64_2022-05-15_00-39-rootfs.tar.zst"
old_sha256 = "a86f43798dfd3f987689f9ea28ab84c18b8387713acf039d0cdc9d7348c55052"
# edition 2021
# DISTRO_NAME=euler_amd64
# ROOTFS_FILE=euler-dde_amd64_2022-08-16_03-59-rootfs.tar.zst
# SHA256SUM=34298ef91c75addf39b0b50b81ceaafb5024e49ed63393c9ee26e2dff3a77ce6
# BUILD_DATE=20220816
# BUILD_TAG=2022-08-16
# STATUS=completed
# VERSION=latest02
# END_TIME=03:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-16
begin = 2022-08-16 03:27:07.882878717+00:00
start-sync_0 = 03:37:16
start-zstd = 03:42:21
start-sync_1 = 03:58:05
end-sync_1 = 03:59:48
end = 2022-08-16 03:59:48.693888900+00:00

[server]
repo = "cake233/euler-dde-amd64"

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
