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

```sh
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
tag = ["kde", "2021-12-28", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "ubuntu-kde_amd64_2021-12-28_00-43.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "45bcc18211d6cbbd6eb6ae46dbd478cd3df666d0b87c03da8e2cb5f6b163ac71"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3892445184

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1113630133

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211221"
previous_tag = "2021-12-21"
previous_file = "ubuntu-kde_amd64_2021-12-21_00-40-rootfs.tar.zst"
previous_sha256 = "a885cb9035c47f4569e707f46d46cae94dcd2d66a4bd5b17f8b6f94decfedd4f"

current_version = "latest01"
current_date = "20211228"
old_file = "ubuntu-kde_amd64_2021-12-14_00-52-rootfs.tar.zst"
old_sha256 = "f7a8b7835c5b81af14e09222edebb24c76692211558ac3ae7b865be9674a46e5"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kde_amd64_2021-12-28_00-43-rootfs.tar.zst
# SHA256SUM=45bcc18211d6cbbd6eb6ae46dbd478cd3df666d0b87c03da8e2cb5f6b163ac71
# BUILD_DATE=20211228
# BUILD_TAG=2021-12-28
# STATUS=completed
# VERSION=latest01
# END_TIME=00:43

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-28
begin = 2021-12-28 00:22:08.898805760+00:00
start-sync_0 = 00:28:23
start-zstd = 00:31:48
start-sync_1 = 00:42:17
end-sync_1 = 00:43:30
end = 2021-12-28 00:43:30.118314469+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.34-0ubuntu3) 2.34'
zsh = 'zsh 5.8 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
