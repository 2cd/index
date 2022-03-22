# ubuntu-lxqt-amd64

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
    --name ubuntu-lxqt-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-lxqt-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-lxqt-amd64 zsh
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

## ubuntu-lxqt-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2022-03-22", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "ubuntu-lxqt_amd64_2022-03-22_00-42.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "bb269225a87f98dd81cc7eabae43c6ed562a014b16cfe368dd904f4222368cb6"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.4G"
tar_bytes = 3570158592

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "902M"
zstd_bytes = 945630348

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220315"
previous_tag = "2022-03-15"
previous_file = "ubuntu-lxqt_amd64_2022-03-15_00-44-rootfs.tar.zst"
previous_sha256 = "8bea4847f1521bbc1b62a980f9f08d85e7f33daf5b8fa16643f50027ac49902e"

current_version = "latest01"
current_date = "20220322"
old_file = "ubuntu-lxqt_amd64_2022-03-08_00-40-rootfs.tar.zst"
old_sha256 = "a5058d17d77c26d3e9388378770ff0582e879fd53636667e36ad36f2c1e07e57"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-lxqt_amd64_2022-03-22_00-42-rootfs.tar.zst
# SHA256SUM=bb269225a87f98dd81cc7eabae43c6ed562a014b16cfe368dd904f4222368cb6
# BUILD_DATE=20220322
# BUILD_TAG=2022-03-22
# STATUS=completed
# VERSION=latest01
# END_TIME=00:42

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-22
begin = 2022-03-22 00:21:17.786991014+00:00
start-sync_0 = 00:27:29
start-zstd = 00:31:08
start-sync_1 = 00:41:53
end-sync_1 = 00:42:59
end = 2022-03-22 00:42:59.056298012+00:00

[server]
repo = "cake233/ubuntu-lxqt-amd64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.8.1 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
