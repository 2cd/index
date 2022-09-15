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
tag = ["kde", "2022-09-15"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-kde_arm64_2022-09-15_00-34.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5e267267bf053b3deda9267220526c3ff33db83d0f8381e1ca87bf7c4a897c0b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1878450688

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "501M"
zstd_bytes = 525165403

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220908"
previous_tag = "2022-09-08"
previous_file = "alpine-kde_arm64_2022-09-08_00-29-rootfs.tar.zst"
previous_sha256 = "bcf75c2c79c240853331d103042b61d44f45da65db8a7a61e5dac550efb4c0a2"

current_version = "latest02"
current_date = "20220915"
old_file = "alpine-kde_arm64_2022-09-01_00-34-rootfs.tar.zst"
old_sha256 = "bc815d0391f069028669a830d1f61c6871502c60f48e76533fa12819dc7e4bd9"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-kde_arm64_2022-09-15_00-34-rootfs.tar.zst
# SHA256SUM=5e267267bf053b3deda9267220526c3ff33db83d0f8381e1ca87bf7c4a897c0b
# BUILD_DATE=20220915
# BUILD_TAG=2022-09-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:34

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-15
begin = 2022-09-15 00:06:48.415960263+00:00
start-sync_0 = 00:24:41
start-zstd = 00:26:28
start-sync_1 = 00:33:50
end-sync_1 = 00:34:33
end = 2022-09-15 00:34:33.677741497+00:00

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (aarch64) Version 1.2.3'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
