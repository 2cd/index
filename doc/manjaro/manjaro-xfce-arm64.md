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
tag = ["xfce", "2022-10-21"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_arm64_2022-10-21_13-02.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "80ec7f3e42f9b66072a406c2a04b0cc55f3518b7333fab8f7d2e1f5ef2efad76"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4369139712

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1282664956

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221007"
previous_tag = "2022-10-07"
previous_file = "manjaro-xfce_arm64_2022-10-07_12-58-rootfs.tar.zst"
previous_sha256 = "f8ecb87badb4777ed1f1e1856d0a615a433bcc9086d1f04c6636340d77a11f8e"

current_version = "latest02"
current_date = "20221021"
old_file = "manjaro-xfce_arm64_2022-09-30_13-05-rootfs.tar.zst"
old_sha256 = "a3a2822fc22d010566b09012c188a9147ae91730b3f0ae7afa219ab32ecd2533"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-xfce_arm64_2022-10-21_13-02-rootfs.tar.zst
# SHA256SUM=80ec7f3e42f9b66072a406c2a04b0cc55f3518b7333fab8f7d2e1f5ef2efad76
# BUILD_DATE=20221021
# BUILD_TAG=2022-10-21
# STATUS=completed
# VERSION=latest02
# END_TIME=13:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-21
begin = 2022-10-21 12:20:52.492683604+00:00
start-sync_0 = 12:36:52
start-zstd = 12:41:28
start-sync_1 = 13:00:47
end-sync_1 = 13:02:11
end = 2022-10-21 13:02:11.515056224+00:00

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
