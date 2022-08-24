# debian-mate-arm64

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
    --name debian-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-mate-arm64 zsh
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

## debian-mate-arm64.toml

```toml
[main]
name = "debian"
tag = ["mate", "2022-08-24"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-mate_arm64_2022-08-24_13-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b993f74b32812c2d566a539c419fd9410d7efe9e6e4357a186d719319e9ced5a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4296708608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1175038733

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220817"
previous_tag = "2022-08-17"
previous_file = "debian-mate_arm64_2022-08-17_13-21-rootfs.tar.zst"
previous_sha256 = "539fd7066b1b13fdc41044b7770fe2e4d34db79142e14f5e25cb0ebdc02bbd6b"

current_version = "latest01"
current_date = "20220824"
old_file = "debian-mate_arm64_2022-08-10_13-16-rootfs.tar.zst"
old_sha256 = "f727d5e0bbcac3cb42848e587dc3abb17f226f8d7f2fe2698c29e7c48d7e6a43"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-mate_arm64_2022-08-24_13-07-rootfs.tar.zst
# SHA256SUM=b993f74b32812c2d566a539c419fd9410d7efe9e6e4357a186d719319e9ced5a
# BUILD_DATE=20220824
# BUILD_TAG=2022-08-24
# STATUS=completed
# VERSION=latest01
# END_TIME=13:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-24
begin = 2022-08-24 12:22:30.311412669+00:00
start-sync_0 = 12:50:01
start-zstd = 12:53:25
start-sync_1 = 13:06:25
end-sync_1 = 13:07:35
end = 2022-08-24 13:07:35.099873742+00:00

[server]
repo = "cake233/debian-mate-arm64"

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
ldd = 'ldd (Debian GLIBC 2.34-4) 2.34'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
