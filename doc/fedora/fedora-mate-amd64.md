# fedora-mate-amd64

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
    --name fedora-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-amd64 zsh
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

## fedora-mate-amd64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2022-03-08"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "fedora-mate_amd64_2022-03-08_13-02.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "85ffe2c6d32351deb2f231a3b787e7a9c789a1135d87d7340d5095b79f5ada8b"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.3G"
tar_bytes = 4602584064

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1423458268

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220301"
previous_tag = "2022-03-01"
previous_file = "fedora-mate_amd64_2022-03-01_13-19-rootfs.tar.zst"
previous_sha256 = "ebd6e81ff5c21cef78d1f93a914003f436e711397f982584466141b30c3e17e8"

current_version = "latest02"
current_date = "20220308"
old_file = "fedora-mate_amd64_2022-02-22_13-13-rootfs.tar.zst"
old_sha256 = "dccdfe676c3eabfbc6ff1f5f01edb95b9b657641c310442c5d8a4729647fffd5"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-mate_amd64_2022-03-08_13-02-rootfs.tar.zst
# SHA256SUM=85ffe2c6d32351deb2f231a3b787e7a9c789a1135d87d7340d5095b79f5ada8b
# BUILD_DATE=20220308
# BUILD_TAG=2022-03-08
# STATUS=completed
# VERSION=latest02
# END_TIME=13:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-08
begin = 2022-03-08 12:36:10.723957634+00:00
start-sync_0 = 12:44:34
start-zstd = 12:48:52
start-sync_1 = 13:01:14
end-sync_1 = 13:02:50
end = 2022-03-08 13:02:50.652019711+00:00

[server]
repo = "cake233/fedora-mate-amd64"

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.8.1 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
