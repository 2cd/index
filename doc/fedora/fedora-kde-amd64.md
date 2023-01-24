# fedora-kde-amd64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not amd64, then install qemu & binfmt-support.
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
    --name fedora-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-kde-amd64 zsh
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

## fedora-kde-amd64.toml

```toml
[main]
name = "fedora"
tag = ["kde", "2023-01-24"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_amd64_2023-01-24_13-22.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ab6055a0c58582a1e5fd55d300bd8b774fbcc982932d5e817079f7a9a46824dd"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.1G"
tar_bytes = 5388164608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1732242910

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230117"
previous_tag = "2023-01-17"
previous_file = "fedora-kde_amd64_2023-01-17_13-42-rootfs.tar.zst"
previous_sha256 = "7fba15e7df7cb3ff2f440adb873273a8fe2ddc63473c5afa62bd405c98ed389c"

current_version = "latest01"
current_date = "20230124"
old_file = "fedora-kde_amd64_2023-01-10_13-17-rootfs.tar.zst"
old_sha256 = "66ba6476dd50d5bd31ac1a65030cfe8256518252e51950b83a61fe0a9f8bc413"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-kde_amd64_2023-01-24_13-22-rootfs.tar.zst
# SHA256SUM=ab6055a0c58582a1e5fd55d300bd8b774fbcc982932d5e817079f7a9a46824dd
# BUILD_DATE=20230124
# BUILD_TAG=2023-01-24
# STATUS=completed
# VERSION=latest01
# END_TIME=13:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-24
begin = 2023-01-24 12:51:56.904832748+00:00
start-sync_0 = 12:59:47
start-zstd = 13:04:00
start-sync_1 = 13:21:13
end-sync_1 = 13:22:53
end = 2023-01-24 13:22:53.920998192+00:00

[server]
repo = "cake233/fedora-kde-amd64"

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
