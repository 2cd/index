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
tag = ["kde", "2022-05-31"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_arm64_2022-05-31_14-53.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8abe774485b24538f2dedbe0f3c0d81b578368f92c69edcd44039e0e0488da98"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.9G"
tar_bytes = 6328918016

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1699522315

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220524"
previous_tag = "2022-05-24"
previous_file = "fedora-kde_arm64_2022-05-24_14-34-rootfs.tar.zst"
previous_sha256 = "345219252d5172326089e45c12f6c0d18436837afc56575161a499d6e1d287b6"

current_version = "latest02"
current_date = "20220531"
old_file = "fedora-kde_arm64_2022-05-17_15-01-rootfs.tar.zst"
old_sha256 = "0d5cfba7475dcccc3c716f5ca6bf8cb8d1795572ee5fc7d6661e901219f1c63c"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-kde_arm64_2022-05-31_14-53-rootfs.tar.zst
# SHA256SUM=8abe774485b24538f2dedbe0f3c0d81b578368f92c69edcd44039e0e0488da98
# BUILD_DATE=20220531
# BUILD_TAG=2022-05-31
# STATUS=completed
# VERSION=latest02
# END_TIME=14:53

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-31
begin = 2022-05-31 12:47:25.820591598+00:00
start-sync_0 = 14:22:38
start-zstd = 14:28:40
start-sync_1 = 14:51:46
end-sync_1 = 14:53:53
end = 2022-05-31 14:53:53.162486108+00:00

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
