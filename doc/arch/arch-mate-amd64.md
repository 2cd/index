# arch-mate-amd64

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
    --name arch-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-mate-amd64 zsh
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

## arch-mate-amd64.toml

```toml
[main]
name = "arch"
tag = ["mate", "2022-11-02"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-mate_amd64_2022-11-02_00-34.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7377b57447a1cb2c982359edaa8898d46f4f6a3d2c29a803f275bd2fa950a649"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.4G"
tar_bytes = 4645370368

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1324789923

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221026"
previous_tag = "2022-10-26"
previous_file = "arch-mate_amd64_2022-10-26_00-55-rootfs.tar.zst"
previous_sha256 = "6e09eb4895591638684996f3291447b1fd9fb12e7fbff1d733ce94f5869ae739"

current_version = "latest01"
current_date = "20221102"
old_file = "arch-mate_amd64_2022-10-19_01-04-rootfs.tar.zst"
old_sha256 = "36a0ffbabdae34616d3527ae6a4884e79d0430852515722db37dcd346a1faa81"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-mate_amd64_2022-11-02_00-34-rootfs.tar.zst
# SHA256SUM=7377b57447a1cb2c982359edaa8898d46f4f6a3d2c29a803f275bd2fa950a649
# BUILD_DATE=20221102
# BUILD_TAG=2022-11-02
# STATUS=completed
# VERSION=latest01
# END_TIME=00:34

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-02
begin = 2022-11-02 00:08:54.305820218+00:00
start-sync_0 = 00:13:22
start-zstd = 00:17:45
start-sync_1 = 00:33:09
end-sync_1 = 00:34:25
end = 2022-11-02 00:34:25.497386817+00:00

[server]
repo = "cake233/arch-mate-amd64"

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
