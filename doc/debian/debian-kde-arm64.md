# debian-kde-arm64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
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
    --name debian-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-kde-arm64 zsh
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

## debian-kde-arm64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2023-05-24"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_arm64_2023-05-24_13-46.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "827cccd31fbff9b699dc928e150c3dc5d37438ca0caff376757fa6e94e76379d"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.1G"
tar_bytes = 6489202176

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1816602258

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230517"
previous_tag = "2023-05-17"
previous_file = "debian-kde_arm64_2023-05-17_13-33-rootfs.tar.zst"
previous_sha256 = "31e900144a12c0a3ec544a59e13c88372a39b46f83a10db94a1552faf9777d0f"

current_version = "latest02"
current_date = "20230524"
old_file = "debian-kde_arm64_2023-05-10_13-48-rootfs.tar.zst"
old_sha256 = "1700459e5ae0d8f60c8d8eeda160b9b80d252d380c06b2a02d2bc3eb71970367"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2023-05-24_13-46-rootfs.tar.zst
# SHA256SUM=827cccd31fbff9b699dc928e150c3dc5d37438ca0caff376757fa6e94e76379d
# BUILD_DATE=20230524
# BUILD_TAG=2023-05-24
# STATUS=completed
# VERSION=latest02
# END_TIME=13:46

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-24
begin = 2023-05-24 12:20:22.277810466+00:00
start-sync_0 = 13:10:34
start-zstd = 13:17:19
start-sync_1 = 13:43:52
end-sync_1 = 13:46:00
end = 2023-05-24 13:46:00.154188544+00:00

[server]
repo = "cake233/debian-kde-arm64"

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
