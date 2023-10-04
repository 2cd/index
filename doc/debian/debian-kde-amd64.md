# debian-kde-amd64

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
    --name debian-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-kde-amd64 zsh
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

## debian-kde-amd64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2023-10-04"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_amd64_2023-10-04_13-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fedf645d585444f3f8a59706608d63da935e070a3ad4cc4f55476ef7c5b64e74"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.6G"
tar_bytes = 5934049280

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1711723798

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230927"
previous_tag = "2023-09-27"
previous_file = "debian-kde_amd64_2023-09-27_13-07-rootfs.tar.zst"
previous_sha256 = "282750083ad26b1500daa884fe20a24f7193d10be6fd5a4badc4bd6b032d1474"

current_version = "latest02"
current_date = "20231004"
old_file = "debian-kde_amd64_2023-09-20_13-08-rootfs.tar.zst"
old_sha256 = "9ceaa36aadae50208c0bcde7ab3babf1cb73c3556cf0cf0b18d808db3d951151"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-kde_amd64_2023-10-04_13-13-rootfs.tar.zst
# SHA256SUM=fedf645d585444f3f8a59706608d63da935e070a3ad4cc4f55476ef7c5b64e74
# BUILD_DATE=20231004
# BUILD_TAG=2023-10-04
# STATUS=completed
# VERSION=latest02
# END_TIME=13:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-04
begin = 2023-10-04 12:37:41.132116050+00:00
start-sync_0 = 12:44:52
start-zstd = 12:50:27
start-sync_1 = 13:11:07
end-sync_1 = 13:13:22
end = 2023-10-04 13:13:22.804380840+00:00

[server]
repo = "cake233/debian-kde-amd64"

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
