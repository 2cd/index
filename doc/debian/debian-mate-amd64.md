# debian-mate-amd64

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
    --name debian-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-mate-amd64 zsh
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

## debian-mate-amd64.toml

```toml
[main]
name = "debian"
tag = ["mate", "2023-10-18"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-mate_amd64_2023-10-18_13-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b96a718bcaa5fa2b302a54660346b0242c88b0bf47d8088acfd83de6a9a23b86"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4192345600

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1129704437

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231011"
previous_tag = "2023-10-11"
previous_file = "debian-mate_amd64_2023-10-11_13-10-rootfs.tar.zst"
previous_sha256 = "6ceec292eff13882db9e45efedb6bd871b1d5202e07de5489a34c83ca65e9c25"

current_version = "latest01"
current_date = "20231018"
old_file = "debian-mate_amd64_2023-10-04_13-05-rootfs.tar.zst"
old_sha256 = "9aa8aadfd545f7c16c18a002851af18243f565b3832445ff3efd2f44980cc980"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-mate_amd64_2023-10-18_13-16-rootfs.tar.zst
# SHA256SUM=b96a718bcaa5fa2b302a54660346b0242c88b0bf47d8088acfd83de6a9a23b86
# BUILD_DATE=20231018
# BUILD_TAG=2023-10-18
# STATUS=completed
# VERSION=latest01
# END_TIME=13:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-18
begin = 2023-10-18 12:46:14.959776376+00:00
start-sync_0 = 12:53:18
start-zstd = 12:57:32
start-sync_1 = 13:14:42
end-sync_1 = 13:16:24
end = 2023-10-18 13:16:24.868132396+00:00

[server]
repo = "cake233/debian-mate-amd64"

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
