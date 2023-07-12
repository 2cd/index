# arch-xfce-armv7

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not armv7, then install qemu & binfmt-support.
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
    --name arch-xfce-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-armv7 zsh
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

## arch-xfce-armv7.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2023-07-12"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_armhf_2023-07-12_01-02.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8723c356ed253bc5ae62bf06b1773b0cf39ad91e4317760fe7229b4a57ef8bbc"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.4G"
tar_bytes = 3546095104

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1120098899

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230705"
previous_tag = "2023-07-05"
previous_file = "arch-xfce_armhf_2023-07-05_01-04-rootfs.tar.zst"
previous_sha256 = "bdd36aacbb0c713d77074a3fea114aba259d0bb94441864cc87d9698c0ef7252"

current_version = "latest02"
current_date = "20230712"
old_file = "arch-xfce_armhf_2023-06-28_01-01-rootfs.tar.zst"
old_sha256 = "ce4b1a8d77525a7769b9824dd84a0becb676d30181d44bb13fd54f20aaabe865"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-xfce_armhf_2023-07-12_01-02-rootfs.tar.zst
# SHA256SUM=8723c356ed253bc5ae62bf06b1773b0cf39ad91e4317760fe7229b4a57ef8bbc
# BUILD_DATE=20230712
# BUILD_TAG=2023-07-12
# STATUS=completed
# VERSION=latest02
# END_TIME=01:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-12
begin = 2023-07-12 00:34:37.074612853+00:00
start-sync_0 = 00:45:13
start-zstd = 00:48:12
start-sync_1 = 01:01:06
end-sync_1 = 01:02:16
end = 2023-07-12 01:02:16.799066866+00:00

[server]
repo = "cake233/arch-xfce-armv7"

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
zsh = 'zsh 5.9 (armv7l-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
