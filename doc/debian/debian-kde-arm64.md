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
tag = ["kde", "2022-05-11"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_arm64_2022-05-11_13-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c75eeb942b899c9d56763a60a949765118b1e73e6bf15f57ad0742091ccf7036"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.2G"
tar_bytes = 5568812544

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1622423310

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220504"
previous_tag = "2022-05-04"
previous_file = "debian-kde_arm64_2022-05-04_15-30-rootfs.tar.zst"
previous_sha256 = "a5410fbdfa133f62555b8cadfb66ab693efbf98f27ded312dd7725b29b6c0488"

current_version = "latest01"
current_date = "20220511"
old_file = "debian-kde_arm64_2022-04-27_13-33-rootfs.tar.zst"
old_sha256 = "641a71248008748ff9d50e2adb14a3709c1fab4bc3b684810bf52e66c2b80624"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2022-05-11_13-26-rootfs.tar.zst
# SHA256SUM=c75eeb942b899c9d56763a60a949765118b1e73e6bf15f57ad0742091ccf7036
# BUILD_DATE=20220511
# BUILD_TAG=2022-05-11
# STATUS=completed
# VERSION=latest01
# END_TIME=13:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-11
begin = 2022-05-11 12:19:16.543906133+00:00
start-sync_0 = 13:00:16
start-zstd = 13:05:21
start-sync_1 = 13:24:33
end-sync_1 = 13:26:09
end = 2022-05-11 13:26:09.216350051+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
