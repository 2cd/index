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
tag = ["dde", "2023-03-15"]
os = "euler"
release = "dde"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "euler-dde_amd64_2023-03-15_00-41.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1d392b1f6e5c1ba5fcadf5984b9054a5007d535654a1935640d0755953f8888c"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.2G"
tar_bytes = 5565359104

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1745847793

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230215"
previous_tag = "2023-02-15"
previous_file = "euler-dde_amd64_2023-02-15_00-41-rootfs.tar.zst"
previous_sha256 = "43391848b7987e2febbd669a63ab4c3635f25469d4c2a2fbbfffc1310705775b"

current_version = "latest02"
current_date = "20230315"
old_file = "euler-dde_amd64_2023-01-15_00-41-rootfs.tar.zst"
old_sha256 = "15d87d4f685728598e520ac18a7e7a34c014b3af7ea150358c3ebab5ffc01827"
# edition 2021
# DISTRO_NAME=euler_amd64
# ROOTFS_FILE=euler-dde_amd64_2023-03-15_00-41-rootfs.tar.zst
# SHA256SUM=1d392b1f6e5c1ba5fcadf5984b9054a5007d535654a1935640d0755953f8888c
# BUILD_DATE=20230315
# BUILD_TAG=2023-03-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:41

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-15
begin = 2023-03-15 00:10:00.903463368+00:00
start-sync_0 = 00:20:51
start-zstd = 00:25:54
start-sync_1 = 00:39:39
end-sync_1 = 00:41:23
end = 2023-03-15 00:41:23.835408542+00:00

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

[port]
tcp = [5902, 36080]
```