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
tag = ["lxqt", "2021-11-28", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "ubuntu-lxqt-amd64_2021-11-28_21-40.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "da94726f994530904060e5440e499be4b860ad99cab7cd3fb163436b035a62e2"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.1G"
tar_bytes = 3223819776

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "822M"
zstd_bytes = 861454490

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211102"
last_tag = ""
last_file = "ubuntu-dev_amd64+lxqt-2021_11-02-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211128"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-lxqt-amd64_2021-11-28_21-40.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest02
# END_TIME=21:40

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 21:09:28.752281998+00:00
start-sync_0 = 21:27:23
start-zstd = 21:30:02
start-sync_1 = 21:39:14
end-sync_1 = 21:40:11
end = 2021-11-28 21:40:11.266196947+00:00

[server]
repo = "cake233/ubuntu-lxqt-amd64"

[server.node1]
name = "cn"
current = false
last = true
split = false

[server.node2]
name = "us"
current = false
last = false
split = false
part = 12

[server.node3]
name = "global"
current = false
last = true
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
