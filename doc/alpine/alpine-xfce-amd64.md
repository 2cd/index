# alpine-xfce-amd64

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
    --name alpine-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-xfce-amd64 zsh
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

## alpine-xfce-amd64.toml

```toml
[main]
name = "alpine"
tag = ["xfce", "2024-02-22"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_amd64_2024-02-22_00-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2800e6da6c1baeb3a3b867afb2c1e32e6050edc230aa932737b5ef94ba9189f9"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1306388992

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "424M"
zstd_bytes = 443716784

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231123"
previous_tag = "2023-11-23"
previous_file = "alpine-xfce_amd64_2023-11-23_00-16-rootfs.tar.zst"
previous_sha256 = "3565abebe2e71215294dd9140fb58e42de15282b5257dbb4be631004d209e117"

current_version = "latest02"
current_date = "20240222"
old_file = "alpine-xfce_amd64_2023-11-16_00-15-rootfs.tar.zst"
old_sha256 = "63f9bb92dfb1fada024bde3909afabf46d4354655e13ee3215613aaf3ee36142"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-xfce_amd64_2024-02-22_00-26-rootfs.tar.zst
# SHA256SUM=2800e6da6c1baeb3a3b867afb2c1e32e6050edc230aa932737b5ef94ba9189f9
# BUILD_DATE=20240222
# BUILD_TAG=2024-02-22
# STATUS=completed
# VERSION=latest02
# END_TIME=00:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-22
begin = 2024-02-22 00:09:22.918398971+00:00
start-sync_0 = 00:20:59
start-zstd = 00:21:53
start-sync_1 = 00:25:54
end-sync_1 = 00:26:21
end = 2024-02-22 00:26:21.574866563+00:00

[server]
repo = "cake233/alpine-xfce-amd64"

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (x86_64) Version 1.2.4_git20230717'
zsh = 'zsh 5.9 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
