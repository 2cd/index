# fedora-xfce-amd64

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
    --name fedora-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it fedora-xfce-amd64 zsh
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

## fedora-xfce-amd64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2021-12-07"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "fedora-xfce_amd64_2021-12-07_13-01.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "cfbe936ac195fcc2bebad82e5f86705d674dc92c37c93590a0ffd1300b822143"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 4020965376

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1309158142

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211130"
previous_tag = "2021-11-30"
previous_file = "fedora-xfce_amd64_2021-11-30_15-52-rootfs.tar.zst"
previous_sha256 = ""

current_version = "latest02"
current_date = "20211207"
old_file = "fedora-xfce-amd64_2021-11-28_22-25-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-xfce_amd64_2021-12-07_13-01-rootfs.tar.zst
# SHA256SUM=cfbe936ac195fcc2bebad82e5f86705d674dc92c37c93590a0ffd1300b822143
# BUILD_DATE=20211207
# BUILD_TAG=2021-12-07
# STATUS=completed
# VERSION=latest02
# END_TIME=13:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-07
begin = 2021-12-07 12:39:52.628838011+00:00
start-sync_0 = 12:45:49
start-zstd = 12:49:09
start-sync_1 = 13:00:11
end-sync_1 = 13:01:38
end = 2021-12-07 13:01:38.114909838+00:00

[server]
repo = "cake233/fedora-xfce-amd64"

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
zsh = 'zsh 5.8 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
