# fedora-kde-arm64

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
    --name fedora-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-kde-arm64 zsh
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

## fedora-kde-arm64.toml

```toml
[main]
name = "fedora"
tag = ["kde", "2023-11-07"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_arm64_2023-11-07_15-25.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0e68f1dc24bf8623f87785665161c9aad7f43e9a11a753f9624946d7e1cf935e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "7.3G"
tar_bytes = 7738350592

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.9G"
zstd_bytes = 1956631502

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231024"
previous_tag = "2023-10-24"
previous_file = "fedora-kde_arm64_2023-10-24_15-51-rootfs.tar.zst"
previous_sha256 = "131700b94255d81bedebb319b0d55442d5697bac1e31e10e6c03c183f31ff88f"

current_version = "latest01"
current_date = "20231107"
old_file = "fedora-kde_arm64_2023-09-26_15-09-rootfs.tar.zst"
old_sha256 = "1386b53524ac057d5fc113d7c71d609f2b4909677b9e01cacf16f21406f72a1f"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-kde_arm64_2023-11-07_15-25-rootfs.tar.zst
# SHA256SUM=0e68f1dc24bf8623f87785665161c9aad7f43e9a11a753f9624946d7e1cf935e
# BUILD_DATE=20231107
# BUILD_TAG=2023-11-07
# STATUS=completed
# VERSION=latest01
# END_TIME=15:25

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-07
begin = 2023-11-07 12:55:27.632015337+00:00
start-sync_0 = 14:49:19
start-zstd = 14:56:01
start-sync_1 = 15:22:46
end-sync_1 = 15:25:15
end = 2023-11-07 15:25:15.260799676+00:00

[server]
repo = "cake233/fedora-kde-arm64"

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
ldd = 'ldd (GNU libc) 2.38.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
