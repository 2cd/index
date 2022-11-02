# debian-kde-amd64

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
    --name debian-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-kde-amd64 zsh
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

## debian-kde-amd64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2022-11-02"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_amd64_2022-11-02_12-54.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "dba4df9514b2e292e4f49c3043769fd242d00976a182f1f8f5b79156a0363052"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.2G"
tar_bytes = 5493866496

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1578560415

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221026"
previous_tag = "2022-10-26"
previous_file = "debian-kde_amd64_2022-10-26_13-02-rootfs.tar.zst"
previous_sha256 = "10f0ed6dd61e4b2af883172a922c6f9ade06195b4480944790d3f06d0115099f"

current_version = "latest01"
current_date = "20221102"
old_file = "debian-kde_amd64_2022-10-19_12-57-rootfs.tar.zst"
old_sha256 = "f956d29aed8fb4c54cf6c087b1b02d6747dfb7c7016a617d033d4863525a8d01"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-kde_amd64_2022-11-02_12-54-rootfs.tar.zst
# SHA256SUM=dba4df9514b2e292e4f49c3043769fd242d00976a182f1f8f5b79156a0363052
# BUILD_DATE=20221102
# BUILD_TAG=2022-11-02
# STATUS=completed
# VERSION=latest01
# END_TIME=12:54

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-02
begin = 2022-11-02 12:22:18.062122005+00:00
start-sync_0 = 12:29:10
start-zstd = 12:34:02
start-sync_1 = 12:53:12
end-sync_1 = 12:54:44
end = 2022-11-02 12:54:44.500298929+00:00

[server]
repo = "cake233/debian-kde-amd64"

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
ldd = 'ldd (Debian GLIBC 2.36-3) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
