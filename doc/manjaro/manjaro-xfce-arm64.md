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

## manjaro-xfce-arm64.toml

```toml
[main]
name = "manjaro"
tag = ["xfce", "2022-02-18"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "manjaro-xfce_arm64_2022-02-18_13-01.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "176b04e256d253f907e3d6e7c92d524ed60c783adc14d1b02678a9dafdda6f5a"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.2G"
tar_bytes = 4494589440

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1276772129

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220211"
previous_tag = "2022-02-11"
previous_file = "manjaro-xfce_arm64_2022-02-11_12-55-rootfs.tar.zst"
previous_sha256 = "755ba1ac47b7f6b759f3da9b221d5e7b967ce5bbac90c631d9723e420a81e4cd"

current_version = "latest01"
current_date = "20220218"
old_file = "manjaro-xfce_arm64_2022-02-04_12-53-rootfs.tar.zst"
old_sha256 = "b8eb7b2ca8be2e0c1afeb2b49e6bb0dc55872bea6da46085fe8b9b3c9b5a6c1d"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-xfce_arm64_2022-02-18_13-01-rootfs.tar.zst
# SHA256SUM=176b04e256d253f907e3d6e7c92d524ed60c783adc14d1b02678a9dafdda6f5a
# BUILD_DATE=20220218
# BUILD_TAG=2022-02-18
# STATUS=completed
# VERSION=latest01
# END_TIME=13:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-18
begin = 2022-02-18 12:22:16.773739975+00:00
start-sync_0 = 12:45:08
start-zstd = 12:48:38
start-sync_1 = 13:00:45
end-sync_1 = 13:01:59
end = 2022-02-18 13:01:59.380880784+00:00

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
ldd = 'ldd (GNU libc) 2.33'
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
