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
tag = ["xfce", "2022-08-23", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_arm64_2022-08-23_01-23.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2ef9e41acbfc66d2f83896d7f654ef6f82a99f8581ccf5b9d39e412e7df2ef59"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3781061120

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "997M"
zstd_bytes = 1044661568

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220816"
previous_tag = "2022-08-16"
previous_file = "ubuntu-xfce_arm64_2022-08-16_01-15-rootfs.tar.zst"
previous_sha256 = "b85ab5b4faa869df0c9e8ef0ec678b932b9277cc8a3266dbaccec758ea0bcd7a"

current_version = "latest01"
current_date = "20220823"
old_file = "ubuntu-xfce_arm64_2022-08-09_01-11-rootfs.tar.zst"
old_sha256 = "a7883c308c4630b1fd23da33efae7b41483484a54e46f028030ea184f1aa8de7"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-xfce_arm64_2022-08-23_01-23-rootfs.tar.zst
# SHA256SUM=2ef9e41acbfc66d2f83896d7f654ef6f82a99f8581ccf5b9d39e412e7df2ef59
# BUILD_DATE=20220823
# BUILD_TAG=2022-08-23
# STATUS=completed
# VERSION=latest01
# END_TIME=01:23

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-23
begin = 2022-08-23 00:22:46.176084665+00:00
start-sync_0 = 01:03:06
start-zstd = 01:06:45
start-sync_1 = 01:22:34
end-sync_1 = 01:23:46
end = 2022-08-23 01:23:46.711837025+00:00

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
