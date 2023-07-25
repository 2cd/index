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
tag = ["kde", "2023-07-25"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_arm64_2023-07-25_13-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "09f3b3b4a6b39ac56c4f7bcaeb1ba0e190f255e437e6616c29326698b52852f5"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.1G"
tar_bytes = 3254321152

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "683M"
zstd_bytes = 715155966

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230718"
previous_tag = "2023-07-18"
previous_file = "fedora-kde_arm64_2023-07-18_13-23-rootfs.tar.zst"
previous_sha256 = "a1404a70bd24374a253c9433171be200372c7602b51c71cb7cab9a09f05152ff"

current_version = "latest01"
current_date = "20230725"
old_file = "fedora-kde_arm64_2023-07-11_13-19-rootfs.tar.zst"
old_sha256 = "7b77e1210075ace63e1fd75367106fbaa26824eea09298fc583ff44f8a70cb91"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-kde_arm64_2023-07-25_13-28-rootfs.tar.zst
# SHA256SUM=09f3b3b4a6b39ac56c4f7bcaeb1ba0e190f255e437e6616c29326698b52852f5
# BUILD_DATE=20230725
# BUILD_TAG=2023-07-25
# STATUS=completed
# VERSION=latest01
# END_TIME=13:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-25
begin = 2023-07-25 12:37:34.983891304+00:00
start-sync_0 = 13:14:37
start-zstd = 13:16:43
start-sync_1 = 13:27:31
end-sync_1 = 13:28:26
end = 2023-07-25 13:28:26.070454415+00:00

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
ldd = 'ldd (GNU libc) 2.37.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
