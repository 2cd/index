# ubuntu-xfce-arm64

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
    --name ubuntu-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-xfce-arm64 zsh
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

## ubuntu-xfce-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2022-07-19", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_arm64_2022-07-19_01-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9fdc265274259ff627dc594fb580acbb262e6c24ffbf5abc139fa85efdd04939"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.5G"
tar_bytes = 3714803712

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "974M"
zstd_bytes = 1020742835

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220712"
previous_tag = "2022-07-12"
previous_file = "ubuntu-xfce_arm64_2022-07-12_01-05-rootfs.tar.zst"
previous_sha256 = "5541a5398f5d6ab4a19001d6848675c224c26c0b1cae948c7a3144d41776c44f"

current_version = "latest01"
current_date = "20220719"
old_file = "ubuntu-xfce_arm64_2022-07-05_01-02-rootfs.tar.zst"
old_sha256 = "bc58e582fae8c1c11c1e1281518c963cb47599ab04634bb8a602d206b7ed79b3"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-xfce_arm64_2022-07-19_01-18-rootfs.tar.zst
# SHA256SUM=9fdc265274259ff627dc594fb580acbb262e6c24ffbf5abc139fa85efdd04939
# BUILD_DATE=20220719
# BUILD_TAG=2022-07-19
# STATUS=completed
# VERSION=latest01
# END_TIME=01:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-19
begin = 2022-07-19 00:19:44.888044750+00:00
start-sync_0 = 00:58:48
start-zstd = 01:02:27
start-sync_1 = 01:17:45
end-sync_1 = 01:18:56
end = 2022-07-19 01:18:56.481481075+00:00

[server]
repo = "cake233/ubuntu-xfce-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
