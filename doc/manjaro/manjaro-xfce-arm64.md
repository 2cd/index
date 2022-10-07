# manjaro-xfce-arm64

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
    --name manjaro-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/manjaro-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it manjaro-xfce-arm64 zsh
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

## manjaro-xfce-arm64.toml

```toml
[main]
name = "manjaro"
tag = ["xfce", "2022-10-07"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_arm64_2022-10-07_12-58.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f8ecb87badb4777ed1f1e1856d0a615a433bcc9086d1f04c6636340d77a11f8e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4368493568

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1265289659

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220930"
previous_tag = "2022-09-30"
previous_file = "manjaro-xfce_arm64_2022-09-30_13-05-rootfs.tar.zst"
previous_sha256 = "a3a2822fc22d010566b09012c188a9147ae91730b3f0ae7afa219ab32ecd2533"

current_version = "latest01"
current_date = "20221007"
old_file = "manjaro-xfce_arm64_2022-09-23_12-59-rootfs.tar.zst"
old_sha256 = "1877b27cd8ac26c86445130147d9d94c42db7c562b423165fb417091fdc31451"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-xfce_arm64_2022-10-07_12-58-rootfs.tar.zst
# SHA256SUM=f8ecb87badb4777ed1f1e1856d0a615a433bcc9086d1f04c6636340d77a11f8e
# BUILD_DATE=20221007
# BUILD_TAG=2022-10-07
# STATUS=completed
# VERSION=latest01
# END_TIME=12:58

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-07
begin = 2022-10-07 12:21:32.639475028+00:00
start-sync_0 = 12:35:25
start-zstd = 12:39:50
start-sync_1 = 12:56:50
end-sync_1 = 12:58:09
end = 2022-10-07 12:58:09.516545714+00:00

[server]
repo = "cake233/manjaro-xfce-arm64"

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
