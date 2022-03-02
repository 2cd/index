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

```sh
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
tag = ["kde", "2022-03-02"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "debian-kde_arm64_2022-03-02_13-23.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "a75406b950e79d58f02d0bef1a2cf2bc0b7a19cdf275ed42c11cb9e9e257c7be"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.3G"
tar_bytes = 5630989824

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1591201032

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220223"
previous_tag = "2022-02-23"
previous_file = "debian-kde_arm64_2022-02-23_13-40-rootfs.tar.zst"
previous_sha256 = "ddd970162c3426015906f5fd2b641e9796eeb78ed76b3f315e00ac044af7792d"

current_version = "latest01"
current_date = "20220302"
old_file = "debian-kde_arm64_2022-02-16_13-40-rootfs.tar.zst"
old_sha256 = "af808233975b4ba962b90cfd1736cf01189c580fe4efecc60296de98b9032565"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2022-03-02_13-23-rootfs.tar.zst
# SHA256SUM=a75406b950e79d58f02d0bef1a2cf2bc0b7a19cdf275ed42c11cb9e9e257c7be
# BUILD_DATE=20220302
# BUILD_TAG=2022-03-02
# STATUS=completed
# VERSION=latest01
# END_TIME=13:23

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-02
begin = 2022-03-02 12:21:32.656203976+00:00
start-sync_0 = 13:02:23
start-zstd = 13:07:24
start-sync_1 = 13:21:34
end-sync_1 = 13:23:15
end = 2022-03-02 13:23:15.096584914+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
