# fedora-xfce-arm64

## How to run it?

```shell
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
    --name fedora-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it fedora-xfce-arm64 zsh
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

## fedora-xfce-arm64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2021-12-07"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "fedora-xfce_arm64_2021-12-07_13-53.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "7ec0c391546ffd1f84088e81a279622529e679b4a190a07ffbf0e68bbb9b13e2"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.1G"
tar_bytes = 5415471616

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1469715913

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211130"
last_tag = "2021-11-30"
last_file = "fedora-xfce_arm64_2021-11-30_17-03-rootfs.tar.zst"
last_sha256 = ""

current_version = "latest01"
current_date = "20211207"
old_file = "fedora-xfce-arm64_2021-11-28_23-36-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-xfce_arm64_2021-12-07_13-53-rootfs.tar.zst
# SHA256SUM=7ec0c391546ffd1f84088e81a279622529e679b4a190a07ffbf0e68bbb9b13e2
# BUILD_DATE=20211207
# BUILD_TAG=2021-12-07
# STATUS=completed
# VERSION=latest01
# END_TIME=13:53

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-07
begin = 2021-12-07 12:39:52.213074768+00:00
start-sync_0 = 13:34:40
start-zstd = 13:39:15
start-sync_1 = 13:51:31
end-sync_1 = 13:53:02
end = 2021-12-07 13:53:02.084883436+00:00

[server]
repo = "cake233/fedora-xfce-arm64"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
last = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"

[version]
zsh = 'zsh 5.8 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
