# debian-xfce-arm64

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
    --name debian-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-xfce-arm64 zsh
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

## debian-xfce-arm64.toml

```toml
[main]
name = "debian"
tag = ["xfce", "2022-12-14"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_arm64_2022-12-14_13-33.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "21359e6ae7a89163619e8bbe0277bba86b8b511643da6687755e38fd08d7607f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.3G"
tar_bytes = 4532308992

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1255891195

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221207"
previous_tag = "2022-12-07"
previous_file = "debian-xfce_arm64_2022-12-07_13-21-rootfs.tar.zst"
previous_sha256 = "604012ee0a296dd7f3eb62e94828b516ec9fc5a2ec7fb662a1361f514200ae7c"

current_version = "latest01"
current_date = "20221214"
old_file = "debian-xfce_arm64_2022-11-30_13-14-rootfs.tar.zst"
old_sha256 = "3ceac3190847a763bd22000e18774bba321034cade4d9a3629b55f0151cf7cff"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-xfce_arm64_2022-12-14_13-33-rootfs.tar.zst
# SHA256SUM=21359e6ae7a89163619e8bbe0277bba86b8b511643da6687755e38fd08d7607f
# BUILD_DATE=20221214
# BUILD_TAG=2022-12-14
# STATUS=completed
# VERSION=latest01
# END_TIME=13:33

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-14
begin = 2022-12-14 12:21:12.638367708+00:00
start-sync_0 = 13:08:04
start-zstd = 13:12:29
start-sync_1 = 13:32:13
end-sync_1 = 13:33:39
end = 2022-12-14 13:33:39.736850396+00:00

[server]
repo = "cake233/debian-xfce-arm64"

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
ldd = 'ldd (Debian GLIBC 2.36-6) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
