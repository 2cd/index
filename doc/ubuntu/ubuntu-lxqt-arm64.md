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
tag = ["lxqt", "2023-09-19", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_arm64_2023-09-19_01-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a03e7179ac274ef898718cf2524bac6ca6a6005946690942eaa2c3fb86fe647e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4810292736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1272643388

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230912"
previous_tag = "2023-09-12"
previous_file = "ubuntu-lxqt_arm64_2023-09-12_01-47-rootfs.tar.zst"
previous_sha256 = "1ff6e8dab1e113fe11f0a79857a52464cf1ee0ce6c2094bf00657f7118831bcf"

current_version = "latest02"
current_date = "20230919"
old_file = "ubuntu-lxqt_arm64_2023-09-05_01-28-rootfs.tar.zst"
old_sha256 = "fb394a6883c146b501c46249dfa0d5dee3eaa4601405dede9691195cd36924b9"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-lxqt_arm64_2023-09-19_01-28-rootfs.tar.zst
# SHA256SUM=a03e7179ac274ef898718cf2524bac6ca6a6005946690942eaa2c3fb86fe647e
# BUILD_DATE=20230919
# BUILD_TAG=2023-09-19
# STATUS=completed
# VERSION=latest02
# END_TIME=01:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-19
begin = 2023-09-19 00:27:57.657949049+00:00
start-sync_0 = 01:06:41
start-zstd = 01:10:35
start-sync_1 = 01:27:29
end-sync_1 = 01:28:47
end = 2023-09-19 01:28:47.258610648+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu4) 2.38'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
