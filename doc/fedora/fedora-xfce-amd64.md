# fedora-xfce-amd64

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
    --name fedora-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-xfce-amd64 zsh
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

## fedora-xfce-amd64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2023-10-17"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_amd64_2023-10-17_13-32.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "cf73eb233964c0bfce32ccb53869009e2daa146139984cd3dcb0783bcecd5456"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4392975872

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1357570968

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231010"
previous_tag = "2023-10-10"
previous_file = "fedora-xfce_amd64_2023-10-10_13-13-rootfs.tar.zst"
previous_sha256 = "e8c467c23d83b55d253da8155d2aed14918fbe1088677cbadb7457af95483c48"

current_version = "latest02"
current_date = "20231017"
old_file = "fedora-xfce_amd64_2023-10-03_13-19-rootfs.tar.zst"
old_sha256 = "0a27c9ad963b3b5176084896816fd2bd9ae583360819096c8e1432adb57483e3"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-xfce_amd64_2023-10-17_13-32-rootfs.tar.zst
# SHA256SUM=cf73eb233964c0bfce32ccb53869009e2daa146139984cd3dcb0783bcecd5456
# BUILD_DATE=20231017
# BUILD_TAG=2023-10-17
# STATUS=completed
# VERSION=latest02
# END_TIME=13:32

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-17
begin = 2023-10-17 13:01:30.734632586+00:00
start-sync_0 = 13:10:14
start-zstd = 13:13:28
start-sync_1 = 13:30:06
end-sync_1 = 13:32:08
end = 2023-10-17 13:32:08.221682753+00:00

[server]
repo = "cake233/fedora-xfce-amd64"

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
ldd = 'ldd (GNU libc) 2.38.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
