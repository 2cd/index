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
tag = ["kde", "2023-02-28", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_amd64_2023-02-28_00-30.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0eb15256b3dc401363f862b3e24cf2cca3b547923823b726efe01153c86b045a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4787887616

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1323573084

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230221"
previous_tag = "2023-02-21"
previous_file = "ubuntu-kde_amd64_2023-02-21_00-31-rootfs.tar.zst"
previous_sha256 = "1a7ddb20db6c1487af2a8135029e8faf476aff58a241b957bd03c13dacd17993"

current_version = "latest01"
current_date = "20230228"
old_file = "ubuntu-kde_amd64_2023-02-14_00-39-rootfs.tar.zst"
old_sha256 = "20183cfd2c15d7424029b1cb86f6bf97fec53b1e044005916e0043e8ae7ac9e8"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kde_amd64_2023-02-28_00-30-rootfs.tar.zst
# SHA256SUM=0eb15256b3dc401363f862b3e24cf2cca3b547923823b726efe01153c86b045a
# BUILD_DATE=20230228
# BUILD_TAG=2023-02-28
# STATUS=completed
# VERSION=latest01
# END_TIME=00:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-28
begin = 2023-02-28 00:02:55.864758183+00:00
start-sync_0 = 00:08:57
start-zstd = 00:13:19
start-sync_1 = 00:29:14
end-sync_1 = 00:30:25
end = 2023-02-28 00:30:25.912722214+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
