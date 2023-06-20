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
tag = ["kde", "2023-06-20"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_amd64_2023-06-20_13-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8f97f742ce9db7524ee7a378bbbd7a9887becd741d2d45edf1dc55d2b3b0700e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.1G"
tar_bytes = 5369316352

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1720486278

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230613"
previous_tag = "2023-06-13"
previous_file = "fedora-kde_amd64_2023-06-13_13-27-rootfs.tar.zst"
previous_sha256 = "2fcd68af3897f0d096d208a535e0bdd1a6dd6f560efa70457d0dd76084a4e260"

current_version = "latest01"
current_date = "20230620"
old_file = "fedora-kde_amd64_2023-06-06_12-36-rootfs.tar.zst"
old_sha256 = "dfa2d97df8159ddf8a9800e806f9a67c9a0faa9ca304fc6923fd4f223584a046"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-kde_amd64_2023-06-20_13-29-rootfs.tar.zst
# SHA256SUM=8f97f742ce9db7524ee7a378bbbd7a9887becd741d2d45edf1dc55d2b3b0700e
# BUILD_DATE=20230620
# BUILD_TAG=2023-06-20
# STATUS=completed
# VERSION=latest01
# END_TIME=13:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-20
begin = 2023-06-20 12:51:49.596680589+00:00
start-sync_0 = 13:00:20
start-zstd = 13:05:30
start-sync_1 = 13:27:51
end-sync_1 = 13:29:49
end = 2023-06-20 13:29:49.513120141+00:00

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
ldd = 'ldd (GNU libc) 2.37.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
