# alpine-kde-arm64

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
    --name alpine-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-kde-arm64 zsh
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

## alpine-kde-arm64.toml

```toml
[main]
name = "alpine"
tag = ["kde", "2022-03-10"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "alpine-kde_arm64_2022-03-10_00-30.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "ad34a151719904a9be3267b2c5f197b44cc7eef5e73a4cb93e8709c69eec10a9"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1758904320

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "482M"
zstd_bytes = 504397201

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220303"
previous_tag = "2022-03-03"
previous_file = "alpine-kde_arm64_2022-03-03_00-31-rootfs.tar.zst"
previous_sha256 = "01e2c44490a819fcff9729bcf11bfe3097fab0faf1b0572239a5267512b41507"

current_version = "latest02"
current_date = "20220310"
old_file = "alpine-kde_arm64_2022-02-24_00-40-rootfs.tar.zst"
old_sha256 = "65808ae95ff15dd6e2ea0ecb735c85d783903da661efe50b494120d380b53062"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-kde_arm64_2022-03-10_00-30-rootfs.tar.zst
# SHA256SUM=ad34a151719904a9be3267b2c5f197b44cc7eef5e73a4cb93e8709c69eec10a9
# BUILD_DATE=20220310
# BUILD_TAG=2022-03-10
# STATUS=completed
# VERSION=latest02
# END_TIME=00:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-10
begin = 2022-03-10 00:06:33.451796729+00:00
start-sync_0 = 00:22:17
start-zstd = 00:23:46
start-sync_1 = 00:30:04
end-sync_1 = 00:30:39
end = 2022-03-10 00:30:39.554826562+00:00

[server]
repo = "cake233/alpine-kde-arm64"

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (aarch64) Version 1.2.2'
zsh = 'zsh 5.8.1 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
