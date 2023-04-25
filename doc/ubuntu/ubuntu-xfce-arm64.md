# ubuntu-xfce-arm64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
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
    --name ubuntu-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-xfce-arm64 zsh
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

## ubuntu-xfce-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2023-04-25", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_arm64_2023-04-25_00-53.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a4bc66df4caaa33dd0593d0d41a62df0f8b054f87fe0521d1fcc69ffd1d3f081"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3873993728

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1015M"
zstd_bytes = 1063801171

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230418"
previous_tag = "2023-04-18"
previous_file = "ubuntu-xfce_arm64_2023-04-18_00-51-rootfs.tar.zst"
previous_sha256 = "df627276e9987f6f24839a3175dda82b0d3840617553bd3600033f8891d421cb"

current_version = "latest02"
current_date = "20230425"
old_file = "ubuntu-xfce_arm64_2023-04-11_00-51-rootfs.tar.zst"
old_sha256 = "b1bc5d598a4f34a02c3809af64f20b3e3bf0c4c521b04ef960764b2aa1cfd98c"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-xfce_arm64_2023-04-25_00-53-rootfs.tar.zst
# SHA256SUM=a4bc66df4caaa33dd0593d0d41a62df0f8b054f87fe0521d1fcc69ffd1d3f081
# BUILD_DATE=20230425
# BUILD_TAG=2023-04-25
# STATUS=completed
# VERSION=latest02
# END_TIME=00:53

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-25
begin = 2023-04-25 00:03:14.378014716+00:00
start-sync_0 = 00:35:18
start-zstd = 00:38:15
start-sync_1 = 00:52:54
end-sync_1 = 00:53:59
end = 2023-04-25 00:53:59.493709209+00:00

[server]
repo = "cake233/ubuntu-xfce-arm64"

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
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
