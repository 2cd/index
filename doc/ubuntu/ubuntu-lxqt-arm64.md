# ubuntu-lxqt-arm64

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
    --name ubuntu-lxqt-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-lxqt-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-lxqt-arm64 zsh
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

## ubuntu-lxqt-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2023-01-24", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_arm64_2023-01-24_00-53.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c60e3d34d39e0d18e525ad12a616b1fc6d87d453e7ad1b777efe2495d3c407f0"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4245072896

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1149462874

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230117"
previous_tag = "2023-01-17"
previous_file = "ubuntu-lxqt_arm64_2023-01-17_00-52-rootfs.tar.zst"
previous_sha256 = "4dba7d34b19429e965a12a7eec658013e35c5e71719a2407d9621e51ba42ecb7"

current_version = "latest02"
current_date = "20230124"
old_file = "ubuntu-lxqt_arm64_2023-01-10_01-04-rootfs.tar.zst"
old_sha256 = "6dfcf0d8b40f150010a2ee516f39f3cff3034e2d47597977315f7dee0774d1ba"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-lxqt_arm64_2023-01-24_00-53-rootfs.tar.zst
# SHA256SUM=c60e3d34d39e0d18e525ad12a616b1fc6d87d453e7ad1b777efe2495d3c407f0
# BUILD_DATE=20230124
# BUILD_TAG=2023-01-24
# STATUS=completed
# VERSION=latest02
# END_TIME=00:53

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-24
begin = 2023-01-24 00:03:04.836402587+00:00
start-sync_0 = 00:34:50
start-zstd = 00:38:10
start-sync_1 = 00:52:07
end-sync_1 = 00:53:12
end = 2023-01-24 00:53:12.332134978+00:00

[server]
repo = "cake233/ubuntu-lxqt-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
