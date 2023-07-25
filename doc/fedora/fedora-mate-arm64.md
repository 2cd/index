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
tag = ["mate", "2023-07-25"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_arm64_2023-07-25_14-57.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4d71d71063b86dd9051045be9228f25b253e12ee7be7e1c0b6ef587db3fdc068"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.8G"
tar_bytes = 7223889920

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1770252552

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230718"
previous_tag = "2023-07-18"
previous_file = "fedora-mate_arm64_2023-07-18_14-56-rootfs.tar.zst"
previous_sha256 = "ce9544c6ce3c96fbac81f06bdab8cfb28e94d110ddeb34b989f412d4ff285934"

current_version = "latest01"
current_date = "20230725"
old_file = "fedora-mate_arm64_2023-07-11_14-59-rootfs.tar.zst"
old_sha256 = "ce563774d67ae2b4caf1aa4f2204a69ffb6a699fd465566264f6db7c8333b538"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-mate_arm64_2023-07-25_14-57-rootfs.tar.zst
# SHA256SUM=4d71d71063b86dd9051045be9228f25b253e12ee7be7e1c0b6ef587db3fdc068
# BUILD_DATE=20230725
# BUILD_TAG=2023-07-25
# STATUS=completed
# VERSION=latest01
# END_TIME=14:57

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-25
begin = 2023-07-25 12:37:33.914878280+00:00
start-sync_0 = 14:24:33
start-zstd = 14:31:25
start-sync_1 = 14:55:55
end-sync_1 = 14:57:58
end = 2023-07-25 14:57:58.519662849+00:00

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
ldd = 'ldd (GNU libc) 2.37.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
