# arch-kde-amd64

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
    --name arch-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-kde-amd64 zsh
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

## arch-kde-amd64.toml

```toml
[main]
name = "arch"
tag = ["kde", "2022-09-23"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-kde_amd64_2022-09-23_05-40.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "dd618e9fe9e4b4de009abb300a7052b46b8733d2b938fbc7bf99330b25898a7c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4730149888

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1369234065

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220921"
previous_tag = "2022-09-21"
previous_file = "arch-kde_amd64_2022-09-21_00-58-rootfs.tar.zst"
previous_sha256 = "60e2100f495a1012dad28051b80eedd2782dd15625b56ebb5f7840b5b1681ad0"

current_version = "latest02"
current_date = "20220923"
old_file = "arch-kde_amd64_2022-09-14_01-06-rootfs.tar.zst"
old_sha256 = "fb1a4b2e00db20ba89861f3c7ac832584276f2ea9ce3f56ea337ff9a409a79e3"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-kde_amd64_2022-09-23_05-40-rootfs.tar.zst
# SHA256SUM=dd618e9fe9e4b4de009abb300a7052b46b8733d2b938fbc7bf99330b25898a7c
# BUILD_DATE=20220923
# BUILD_TAG=2022-09-23
# STATUS=completed
# VERSION=latest02
# END_TIME=05:40

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-23
begin = 2022-09-23 05:09:51.062012229+00:00
start-sync_0 = 05:16:12
start-zstd = 05:20:45
start-sync_1 = 05:39:02
end-sync_1 = 05:40:22
end = 2022-09-23 05:40:22.334001799+00:00

[server]
repo = "cake233/arch-kde-amd64"

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
ldd = 'ldd (GNU libc) 2.36'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
