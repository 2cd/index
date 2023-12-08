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
tag = ["xfce", "2023-12-08"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_arm64_2023-12-08_12-49.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "01426629f07ef6aa5887290f165dcc339f3ab471a62ba79e10875118fa6b38d1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.4G"
tar_bytes = 4638433792

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1307113339

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231124"
previous_tag = "2023-11-24"
previous_file = "manjaro-xfce_arm64_2023-11-24_12-42-rootfs.tar.zst"
previous_sha256 = "2193d8f461d5d51e9730e6df75f9cde32e0a5788350bcabfa2f354570260e7cf"

current_version = "latest01"
current_date = "20231208"
old_file = "manjaro-xfce_arm64_2023-11-17_12-48-rootfs.tar.zst"
old_sha256 = "a827ab5f4e5f6083c608ef78b7271b5b37b6c6ed5970da4560cd3f3689c060a0"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-xfce_arm64_2023-12-08_12-49-rootfs.tar.zst
# SHA256SUM=01426629f07ef6aa5887290f165dcc339f3ab471a62ba79e10875118fa6b38d1
# BUILD_DATE=20231208
# BUILD_TAG=2023-12-08
# STATUS=completed
# VERSION=latest01
# END_TIME=12:49

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-08
begin = 2023-12-08 12:21:00.927495070+00:00
start-sync_0 = 12:31:44
start-zstd = 12:34:10
start-sync_1 = 12:48:09
end-sync_1 = 12:49:03
end = 2023-12-08 12:49:03.962842293+00:00

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
