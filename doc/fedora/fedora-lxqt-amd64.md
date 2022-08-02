# fedora-lxqt-amd64

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
    --name fedora-lxqt-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-lxqt-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-lxqt-amd64 zsh
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

## fedora-lxqt-amd64.toml

```toml
[main]
name = "fedora"
tag = ["lxqt", "2022-08-02"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-lxqt_amd64_2022-08-02_13-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "37ab57407a66c9fd2727e28c3e95a78a17b3a8316756030bb49d1ab6e645eb9b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.3G"
tar_bytes = 3497725440

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "922M"
zstd_bytes = 966024281

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211102"
previous_tag = ""
previous_file = "fedora-rawhide_amd64+lxqt-2021_11-02-rootfs.tar.zst"
previous_sha256 = "fc546284d21dbef914c7cafb3d7006b02cae4a8633067745fd826e8f3597cb70"

current_version = "latest02"
current_date = "20220802"
old_file = "fedora-rawhide_amd64+lxqt-2021_10-26-rootfs.tar.zst"
old_sha256 = "e507e03c2fba7bde2a8166834367ba9a4d407b87840550d3504aab03a9f877c1"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-lxqt_amd64_2022-08-02_13-14-rootfs.tar.zst
# SHA256SUM=37ab57407a66c9fd2727e28c3e95a78a17b3a8316756030bb49d1ab6e645eb9b
# BUILD_DATE=20220802
# BUILD_TAG=2022-08-02
# STATUS=completed
# VERSION=latest02
# END_TIME=13:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-02
begin = 2022-08-02 12:50:08.684607101+00:00
start-sync_0 = 12:54:39
start-zstd = 12:57:40
start-sync_1 = 13:13:21
end-sync_1 = 13:14:27
end = 2022-08-02 13:14:27.967087375+00:00

[server]
repo = "cake233/fedora-lxqt-amd64"

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
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
