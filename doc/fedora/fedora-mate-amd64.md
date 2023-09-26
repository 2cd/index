# fedora-mate-amd64

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
    --name fedora-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-amd64 zsh
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

## fedora-mate-amd64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2023-09-26"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_amd64_2023-09-26_13-24.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f7145b3244756c7ca20c6b11e17f1ab610dd60ee8df6e48b350bbfa745d09942"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.0G"
tar_bytes = 5297881088

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1562934619

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230919"
previous_tag = "2023-09-19"
previous_file = "fedora-mate_amd64_2023-09-19_13-26-rootfs.tar.zst"
previous_sha256 = "545e34fed83791bff09d8feb86ccbb44acda44b295ffe371c576cf8fcf1a2302"

current_version = "latest02"
current_date = "20230926"
old_file = "fedora-mate_amd64_2023-09-12_13-06-rootfs.tar.zst"
old_sha256 = "3b40b14937852596273ad2f873d7f8485cd8616634351a51af416d46aaefe806"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-mate_amd64_2023-09-26_13-24-rootfs.tar.zst
# SHA256SUM=f7145b3244756c7ca20c6b11e17f1ab610dd60ee8df6e48b350bbfa745d09942
# BUILD_DATE=20230926
# BUILD_TAG=2023-09-26
# STATUS=completed
# VERSION=latest02
# END_TIME=13:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-26
begin = 2023-09-26 12:53:06.574681098+00:00
start-sync_0 = 12:59:38
start-zstd = 13:04:27
start-sync_1 = 13:22:22
end-sync_1 = 13:24:06
end = 2023-09-26 13:24:06.638197113+00:00

[server]
repo = "cake233/fedora-mate-amd64"

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
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
