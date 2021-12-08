# ubuntu-lxqt-amd64

## How to run it?

```shell
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

```shell
    docker exex -it ubuntu-lxqt-amd64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```shell
    startvnc
```

or

```shell
    startx11vnc
```

or

```shell
    novnc
```

Note:

If you want to use novnc, then open your browser, and type the address:

```
localhost:36081
```

If you want to use tiger/x11vnc, then open vnc viewer, then type the address:

```
localhost:5903
```

## ubuntu-lxqt-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2021-12-07", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "ubuntu-lxqt_amd64_2021-12-07_00-53.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "626c5ef28715780d0d770c2db892bd5325a13c12ce22186d31f365914269d7af"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.1G"
tar_bytes = 3269202944

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "831M"
zstd_bytes = 871069659

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211130"
previous_tag = "2021-11-30"
previous_file = "ubuntu-lxqt_amd64_2021-11-30_14-08-rootfs.tar.zst"
previous_sha256 = ""

current_version = "latest02"
current_date = "20211207"
old_file = "ubuntu-lxqt-amd64_2021-11-28_21-40-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-lxqt_amd64_2021-12-07_00-53-rootfs.tar.zst
# SHA256SUM=626c5ef28715780d0d770c2db892bd5325a13c12ce22186d31f365914269d7af
# BUILD_DATE=20211207
# BUILD_TAG=2021-12-07
# STATUS=completed
# VERSION=latest02
# END_TIME=00:53

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-07
begin = 2021-12-07 00:23:07.131933389+00:00
start-sync_0 = 00:39:46
start-zstd = 00:43:00
start-sync_1 = 00:52:33
end-sync_1 = 00:53:38
end = 2021-12-07 00:53:38.823802182+00:00

[server]
repo = "cake233/ubuntu-lxqt-amd64"

[server.node1]
name = "cn"
current = false
previous = true
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
zsh = 'zsh 5.8 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
