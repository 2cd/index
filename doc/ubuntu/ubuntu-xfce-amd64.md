# ubuntu-xfce-amd64

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
    --name ubuntu-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-xfce-amd64 zsh
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

## ubuntu-xfce-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2023-12-26", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_amd64_2023-12-26_00-56.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c50bb39efaa04232f45d915419bb58365df7282a15cfcf32404e6f3f0d3023e2"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4314927104

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1172853990

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231128"
previous_tag = "2023-11-28"
previous_file = "ubuntu-xfce_amd64_2023-11-28_00-44-rootfs.tar.zst"
previous_sha256 = "24e4f54ca72a5187a485f13f658856991174b15aa2bfbe8e5698656545714cf1"

current_version = "latest02"
current_date = "20231226"
old_file = "ubuntu-xfce_amd64_2023-11-21_00-43-rootfs.tar.zst"
old_sha256 = "caf9ba3bcf4d53bee683cc0fd6c476fa44d89de3f31cc0c53b180d1ed9c7fd11"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-xfce_amd64_2023-12-26_00-56-rootfs.tar.zst
# SHA256SUM=c50bb39efaa04232f45d915419bb58365df7282a15cfcf32404e6f3f0d3023e2
# BUILD_DATE=20231226
# BUILD_TAG=2023-12-26
# STATUS=completed
# VERSION=latest02
# END_TIME=00:56

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-26
begin = 2023-12-26 00:36:03.429549204+00:00
start-sync_0 = 00:41:42
start-zstd = 00:44:10
start-sync_1 = 00:55:25
end-sync_1 = 00:56:18
end = 2023-12-26 00:56:18.396187433+00:00

[server]
repo = "cake233/ubuntu-xfce-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-3ubuntu1) 2.38'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
