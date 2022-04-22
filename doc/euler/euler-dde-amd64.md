# euler-dde-amd64

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
    --name euler-dde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/euler-dde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it euler-dde-amd64 zsh
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

## euler-dde-amd64.toml

```toml
[main]
name = "euler"
tag = ["dde", "2022-04-22"]
os = "euler"
release = "dde"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true
syntax_version = "0.0.0-alpha.3"

[file]
name = "euler-dde_amd64_2022-04-22_03-49.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "05160fbdaf6cb0ee3826fd6e8832682ffc920b709a501e2936982f807abc0333"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.3G"
tar_bytes = 4557050368

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1340380815

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220422"
previous_tag = "2022-04-22"
previous_file = "euler-dde_amd64_2022-04-22_01-31-rootfs.tar.zst"
previous_sha256 = "e1cff8d6ac9c08bc2856404cfae37a94a72502f1fd2088b01d194b871a3d6a64"

current_version = "latest02"
current_date = "20220422"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=euler_amd64
# ROOTFS_FILE=euler-dde_amd64_2022-04-22_03-49-rootfs.tar.zst
# SHA256SUM=05160fbdaf6cb0ee3826fd6e8832682ffc920b709a501e2936982f807abc0333
# BUILD_DATE=20220422
# BUILD_TAG=2022-04-22
# STATUS=completed
# VERSION=latest02
# END_TIME=03:49

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-22
begin = 2022-04-22 03:21:12.977952411+00:00
start-sync_0 = 03:31:06
start-zstd = 03:36:14
start-sync_1 = 03:47:57
end-sync_1 = 03:49:25
end = 2022-04-22 03:49:25.712367382+00:00

[server]
repo = "cake233/euler-dde-amd64"

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

[port]
tcp = [5902, 36080]
```
