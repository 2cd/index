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
tag = ["xfce", "2023-11-23"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_amd64_2023-11-23_00-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3565abebe2e71215294dd9140fb58e42de15282b5257dbb4be631004d209e117"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1329746432

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "422M"
zstd_bytes = 442149902

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231116"
previous_tag = "2023-11-16"
previous_file = "alpine-xfce_amd64_2023-11-16_00-15-rootfs.tar.zst"
previous_sha256 = "63f9bb92dfb1fada024bde3909afabf46d4354655e13ee3215613aaf3ee36142"

current_version = "latest01"
current_date = "20231123"
old_file = "alpine-xfce_amd64_2023-11-09_00-10-rootfs.tar.zst"
old_sha256 = "875ce2563c56304433fb9e1673ba830dffd2462731bac8379393a0d20e80ca07"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-xfce_amd64_2023-11-23_00-16-rootfs.tar.zst
# SHA256SUM=3565abebe2e71215294dd9140fb58e42de15282b5257dbb4be631004d209e117
# BUILD_DATE=20231123
# BUILD_TAG=2023-11-23
# STATUS=completed
# VERSION=latest01
# END_TIME=00:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-23
begin = 2023-11-23 00:07:42.287814582+00:00
start-sync_0 = 00:10:37
start-zstd = 00:11:32
start-sync_1 = 00:15:37
end-sync_1 = 00:16:07
end = 2023-11-23 00:16:07.308796548+00:00

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
