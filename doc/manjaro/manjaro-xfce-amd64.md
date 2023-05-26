# manjaro-xfce-amd64

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
    --name manjaro-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/manjaro-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it manjaro-xfce-amd64 zsh
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

## manjaro-xfce-amd64.toml

```toml
[main]
name = "manjaro"
tag = ["xfce", "2023-05-26"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_amd64_2023-05-26_12-45.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "cb1c4715f921c65a94b98e4bce40533a51bb2dd0fd51c1821fc47cb0e29c9383"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 4044772352

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1199115088

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230519"
previous_tag = "2023-05-19"
previous_file = "manjaro-xfce_amd64_2023-05-19_12-43-rootfs.tar.zst"
previous_sha256 = "349d7a78c00f8fbd4d1cc93f6e11b7ae3b5568ea0a35ffbaaee3fe03978a3e66"

current_version = "latest01"
current_date = "20230526"
old_file = "manjaro-xfce_amd64_2023-05-12_12-48-rootfs.tar.zst"
old_sha256 = "b73e149d1974e9057c81cddecf3d1fd68136a4a583c66b049f79ed70e3b58f7a"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-xfce_amd64_2023-05-26_12-45-rootfs.tar.zst
# SHA256SUM=cb1c4715f921c65a94b98e4bce40533a51bb2dd0fd51c1821fc47cb0e29c9383
# BUILD_DATE=20230526
# BUILD_TAG=2023-05-26
# STATUS=completed
# VERSION=latest01
# END_TIME=12:45

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-26
begin = 2023-05-26 12:23:16.136253417+00:00
start-sync_0 = 12:26:40
start-zstd = 12:29:31
start-sync_1 = 12:44:26
end-sync_1 = 12:45:32
end = 2023-05-26 12:45:32.821776716+00:00

[server]
repo = "cake233/manjaro-xfce-amd64"

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
