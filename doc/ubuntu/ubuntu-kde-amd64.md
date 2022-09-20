# ubuntu-kde-amd64

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
    --name ubuntu-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-amd64 zsh
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

## ubuntu-kde-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2022-09-20", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_amd64_2022-09-20_00-52.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d0fd8e0e90af0f8a8754750490e825bbbe0635dc79aea8702523266afde500a4"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.4G"
tar_bytes = 4682797568

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1278452460

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220913"
previous_tag = "2022-09-13"
previous_file = "ubuntu-kde_amd64_2022-09-13_00-59-rootfs.tar.zst"
previous_sha256 = "e80edd7c431196f05608cd1ea476fac1286974461f01b05b1ca805f4f438705d"

current_version = "latest02"
current_date = "20220920"
old_file = "ubuntu-kde_amd64_2022-09-06_00-51-rootfs.tar.zst"
old_sha256 = "d075c0c31a0aff7424cbaf64e6f45a315fdb6ca3b633801ddb99aa03885cdef9"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kde_amd64_2022-09-20_00-52-rootfs.tar.zst
# SHA256SUM=d0fd8e0e90af0f8a8754750490e825bbbe0635dc79aea8702523266afde500a4
# BUILD_DATE=20220920
# BUILD_TAG=2022-09-20
# STATUS=completed
# VERSION=latest02
# END_TIME=00:52

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-20
begin = 2022-09-20 00:19:17.808077366+00:00
start-sync_0 = 00:27:08
start-zstd = 00:32:34
start-sync_1 = 00:51:01
end-sync_1 = 00:52:23
end = 2022-09-20 00:52:23.736378585+00:00

[server]
repo = "cake233/ubuntu-kde-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu2) 2.36'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
