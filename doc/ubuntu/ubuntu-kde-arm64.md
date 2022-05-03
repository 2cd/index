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
tag = ["kde", "2022-05-03", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_arm64_2022-05-03_01-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "57aa98913879a1834d25d52d5de7779cb9b431e07ce761bc87e3dc0797ac5587"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.2G"
tar_bytes = 4458745856

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1230766743

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220427"
previous_tag = "2022-04-27"
previous_file = "ubuntu-kde_arm64_2022-04-27_14-32-rootfs.tar.zst"
previous_sha256 = "0c9a56e253c8916962583f0b224d2357089f0957d77bf2d6801c061251198f5c"

current_version = "latest01"
current_date = "20220503"
old_file = "ubuntu-kde_arm64_2022-04-26_01-17-rootfs.tar.zst"
old_sha256 = "08a9530193d58a649dcefee38712b80993c2ef88f76950b6db7ad5c3f2d782db"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-kde_arm64_2022-05-03_01-16-rootfs.tar.zst
# SHA256SUM=57aa98913879a1834d25d52d5de7779cb9b431e07ce761bc87e3dc0797ac5587
# BUILD_DATE=20220503
# BUILD_TAG=2022-05-03
# STATUS=completed
# VERSION=latest01
# END_TIME=01:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-03
begin = 2022-05-03 00:20:43.833360275+00:00
start-sync_0 = 00:56:14
start-zstd = 00:59:55
start-sync_1 = 01:15:17
end-sync_1 = 01:16:31
end = 2022-05-03 01:16:31.748379732+00:00

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
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
