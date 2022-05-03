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
tag = ["kde", "2022-05-03", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_amd64_2022-05-03_00-46.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "127760c43ee748bcb81af05d49c71cf7721bfb303ee55619371e145b2a2803bd"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4289301504

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1156687284

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220427"
previous_tag = "2022-04-27"
previous_file = "ubuntu-kde_amd64_2022-04-27_14-02-rootfs.tar.zst"
previous_sha256 = "62480614d61d1ae5b2710d814ce49e9eb8298d5802a8e6fa7eef94fc20127af9"

current_version = "latest01"
current_date = "20220503"
old_file = "ubuntu-kde_amd64_2022-04-26_00-52-rootfs.tar.zst"
old_sha256 = "b9d8b685f53c2b6074b020c81ed9a5732af521f9f93b8c8d0754aafe46f6f5ca"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kde_amd64_2022-05-03_00-46-rootfs.tar.zst
# SHA256SUM=127760c43ee748bcb81af05d49c71cf7721bfb303ee55619371e145b2a2803bd
# BUILD_DATE=20220503
# BUILD_TAG=2022-05-03
# STATUS=completed
# VERSION=latest01
# END_TIME=00:46

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-03
begin = 2022-05-03 00:20:47.002871382+00:00
start-sync_0 = 00:27:06
start-zstd = 00:30:47
start-sync_1 = 00:45:45
end-sync_1 = 00:46:55
end = 2022-05-03 00:46:55.738580671+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.8.1 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
