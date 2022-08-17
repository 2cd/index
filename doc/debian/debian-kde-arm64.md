# debian-kde-arm64

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
    --name debian-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-kde-arm64 zsh
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

## debian-kde-arm64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2022-08-17"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_arm64_2022-08-17_13-30.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7c0bbb9841dfef8cc17fe81ff7e05c759d23b2da6f07eb0cc59e6461e47ff94e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.9G"
tar_bytes = 6320924672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1816824781

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220810"
previous_tag = "2022-08-10"
previous_file = "debian-kde_arm64_2022-08-10_13-41-rootfs.tar.zst"
previous_sha256 = "3bde11d9cd81d5ffdc0347c5003616644e1be63f294da2a6a76f8db8c242aa37"

current_version = "latest02"
current_date = "20220817"
old_file = "debian-kde_arm64_2022-07-13_13-31-rootfs.tar.zst"
old_sha256 = "bb4767c4855b62e588048cd85088cae54c72cad5b70540bb5ac8ca0788b29aa8"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2022-08-17_13-30-rootfs.tar.zst
# SHA256SUM=7c0bbb9841dfef8cc17fe81ff7e05c759d23b2da6f07eb0cc59e6461e47ff94e
# BUILD_DATE=20220817
# BUILD_TAG=2022-08-17
# STATUS=completed
# VERSION=latest02
# END_TIME=13:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-17
begin = 2022-08-17 12:20:35.418906485+00:00
start-sync_0 = 13:00:35
start-zstd = 13:06:17
start-sync_1 = 13:28:46
end-sync_1 = 13:30:29
end = 2022-08-17 13:30:29.165346807+00:00

[server]
repo = "cake233/debian-kde-arm64"

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
ldd = 'ldd (Debian GLIBC 2.34-4) 2.34'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
