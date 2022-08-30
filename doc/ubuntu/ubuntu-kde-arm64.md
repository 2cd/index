# ubuntu-kde-arm64

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
    --name ubuntu-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-arm64 zsh
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

## ubuntu-kde-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2022-08-30", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_arm64_2022-08-30_01-21.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6d04c394115979be751a1a8c1383c5eca54f31cdaddb81af5db0de061bdd5ff5"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.7G"
tar_bytes = 4972162560

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1364098396

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220823"
previous_tag = "2022-08-23"
previous_file = "ubuntu-kde_arm64_2022-08-23_01-22-rootfs.tar.zst"
previous_sha256 = "d484241c36129c860a1973f74429eb347930ada865f963680f23e93488db590d"

current_version = "latest01"
current_date = "20220830"
old_file = "ubuntu-kde_arm64_2022-08-16_01-21-rootfs.tar.zst"
old_sha256 = "cbd6b4e67597fc7a55787dbffe53ddddb751b65538f274870f04206d761dcf88"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-kde_arm64_2022-08-30_01-21-rootfs.tar.zst
# SHA256SUM=6d04c394115979be751a1a8c1383c5eca54f31cdaddb81af5db0de061bdd5ff5
# BUILD_DATE=20220830
# BUILD_TAG=2022-08-30
# STATUS=completed
# VERSION=latest01
# END_TIME=01:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-30
begin = 2022-08-30 00:06:58.936827461+00:00
start-sync_0 = 00:54:42
start-zstd = 01:01:09
start-sync_1 = 01:20:05
end-sync_1 = 01:21:35
end = 2022-08-30 01:21:35.572754476+00:00

[server]
repo = "cake233/ubuntu-kde-arm64"

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
