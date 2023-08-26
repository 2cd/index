# fedora-mate-arm64

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
    --name fedora-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-arm64 zsh
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

## fedora-mate-arm64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2023-08-26"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_arm64_2023-08-26_09-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a77c880c40170b20a21890ce7e0797be46ea4b2dfb3482c32fb947de5be1165e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.5G"
tar_bytes = 6937439744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1686933259

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230822"
previous_tag = "2023-08-22"
previous_file = "fedora-mate_arm64_2023-08-22_14-29-rootfs.tar.zst"
previous_sha256 = "798044a44545d5649566325bc57265e2007f5b9fe8198ff06e1f442fb304a542"

current_version = "latest02"
current_date = "20230826"
old_file = "fedora-mate_arm64_2023-08-15_14-21-rootfs.tar.zst"
old_sha256 = "cc18c062b4db0aca80610470292f928d54b4bc340b2c347906e21722a4781b8e"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-mate_arm64_2023-08-26_09-28-rootfs.tar.zst
# SHA256SUM=a77c880c40170b20a21890ce7e0797be46ea4b2dfb3482c32fb947de5be1165e
# BUILD_DATE=20230826
# BUILD_TAG=2023-08-26
# STATUS=completed
# VERSION=latest02
# END_TIME=09:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-26
begin = 2023-08-26 07:11:50.320287552+00:00
start-sync_0 = 09:01:38
start-zstd = 09:06:40
start-sync_1 = 09:27:10
end-sync_1 = 09:28:50
end = 2023-08-26 09:28:50.508557265+00:00

[server]
repo = "cake233/fedora-mate-arm64"

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
ldd = 'ldd (GNU libc) 2.38'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
