# alpine-xfce-amd64

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
    --name alpine-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-xfce-amd64 zsh
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

## alpine-xfce-amd64.toml

```toml
[main]
name = "alpine"
tag = ["xfce", "2023-01-05"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_amd64_2023-01-05_00-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5fbd33860522f7eff66ac2559e9fb1c3c3511155a385f0033e6abb1269006aad"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "992M"
tar_bytes = 1039335936

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "336M"
zstd_bytes = 351967397

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221229"
previous_tag = "2022-12-29"
previous_file = "alpine-xfce_amd64_2022-12-29_00-15-rootfs.tar.zst"
previous_sha256 = "28bfbd8e607182c5ace525d264aa273575cd4dfac3f85e620ab6eb3383525b6a"

current_version = "latest01"
current_date = "20230105"
old_file = "alpine-xfce_amd64_2022-12-22_00-13-rootfs.tar.zst"
old_sha256 = "d85975f5f2c305b7fd5c280ed3a2e217eefd9a4ec9ea1d44142841a569709e2e"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-xfce_amd64_2023-01-05_00-13-rootfs.tar.zst
# SHA256SUM=5fbd33860522f7eff66ac2559e9fb1c3c3511155a385f0033e6abb1269006aad
# BUILD_DATE=20230105
# BUILD_TAG=2023-01-05
# STATUS=completed
# VERSION=latest01
# END_TIME=00:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-05
begin = 2023-01-05 00:07:05.433691442+00:00
start-sync_0 = 00:08:51
start-zstd = 00:09:46
start-sync_1 = 00:13:01
end-sync_1 = 00:13:25
end = 2023-01-05 00:13:25.473747819+00:00

[server]
repo = "cake233/alpine-xfce-amd64"

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (x86_64) Version 1.2.3'
zsh = 'zsh 5.9 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
