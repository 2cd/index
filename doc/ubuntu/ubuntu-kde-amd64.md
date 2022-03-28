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
tag = ["kde", "2022-03-28", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "ubuntu-kde_amd64_2022-03-28_23-51.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "e28ad6b357370c88d65da44119a125630bf3749c4ef947a30b912702c012bcd2"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.2G"
tar_bytes = 4412420608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1202734378

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220324"
previous_tag = "2022-03-24"
previous_file = "ubuntu-kde_amd64_2022-03-24_19-04-rootfs.tar.zst"
previous_sha256 = "dc6fc982ded4de38e461366786efd251350cf831e47a60ee41228fee1bdfc00d"

current_version = "latest01"
current_date = "20220328"
old_file = "ubuntu-kde_amd64_2022-03-22_00-47-rootfs.tar.zst"
old_sha256 = "bf3eabf723ae6ca6d25b26a6a6b8d2d1fbd2f4e4840c564f3efd49e071e6895c"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kde_amd64_2022-03-28_23-51-rootfs.tar.zst
# SHA256SUM=e28ad6b357370c88d65da44119a125630bf3749c4ef947a30b912702c012bcd2
# BUILD_DATE=20220328
# BUILD_TAG=2022-03-28
# STATUS=completed
# VERSION=latest01
# END_TIME=23:51

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-28
begin = 2022-03-28 23:19:09.590690900+00:00
start-sync_0 = 23:26:43
start-zstd = 23:31:35
start-sync_1 = 23:50:31
end-sync_1 = 23:51:53
end = 2022-03-28 23:51:53.631020282+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.8.1 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
