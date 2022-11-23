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
tag = ["kde", "2022-11-23"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-kde_amd64_2022-11-23_01-02.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "55bb0ed1199a347068109dcd23d2dd09b658ac79bf766ea690cd5a41bd1a3980"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4822541312

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1406998806

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221120"
previous_tag = "2022-11-20"
previous_file = "arch-kde_amd64_2022-11-20_21-12-rootfs.tar.zst"
previous_sha256 = "e5432f650fc3466cb7f6f8c50347f686ebc6e5eabb8498d0e34d2f169ba5bc25"

current_version = "latest01"
current_date = "20221123"
old_file = "arch-kde_amd64_2022-11-16_00-40-rootfs.tar.zst"
old_sha256 = "a53a11484af87642231e21a8307b01581349fc6d5d23526ce9ea9d1d198bd84e"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-kde_amd64_2022-11-23_01-02-rootfs.tar.zst
# SHA256SUM=55bb0ed1199a347068109dcd23d2dd09b658ac79bf766ea690cd5a41bd1a3980
# BUILD_DATE=20221123
# BUILD_TAG=2022-11-23
# STATUS=completed
# VERSION=latest01
# END_TIME=01:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-23
begin = 2022-11-23 00:32:33.849216036+00:00
start-sync_0 = 00:36:58
start-zstd = 00:41:44
start-sync_1 = 01:00:53
end-sync_1 = 01:02:12
end = 2022-11-23 01:02:12.478296231+00:00

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
