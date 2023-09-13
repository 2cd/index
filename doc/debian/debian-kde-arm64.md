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
tag = ["kde", "2023-09-13"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_arm64_2023-09-13_13-48.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "39bea54247b4c5d83c789ee6e170f1b0f6e11d49f7e33ad1a676e50b1c07a560"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.1G"
tar_bytes = 6536791040

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.8G"
zstd_bytes = 1827516740

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230906"
previous_tag = "2023-09-06"
previous_file = "debian-kde_arm64_2023-09-06_13-49-rootfs.tar.zst"
previous_sha256 = "ed915a8d13bb8d24298c01c53374659fc5fdc04a653532e9ddbdc414590f935f"

current_version = "latest01"
current_date = "20230913"
old_file = "debian-kde_arm64_2023-08-30_13-35-rootfs.tar.zst"
old_sha256 = "6ce3d9fb01056b9408433cbac04d97588de5088fc5747a9b6c884a5898c9bddf"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2023-09-13_13-48-rootfs.tar.zst
# SHA256SUM=39bea54247b4c5d83c789ee6e170f1b0f6e11d49f7e33ad1a676e50b1c07a560
# BUILD_DATE=20230913
# BUILD_TAG=2023-09-13
# STATUS=completed
# VERSION=latest01
# END_TIME=13:48

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-13
begin = 2023-09-13 12:23:45.620777796+00:00
start-sync_0 = 13:16:34
start-zstd = 13:21:41
start-sync_1 = 13:45:48
end-sync_1 = 13:48:16
end = 2023-09-13 13:48:16.244179682+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-8) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
