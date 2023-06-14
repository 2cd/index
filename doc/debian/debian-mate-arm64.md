# debian-mate-arm64

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
    --name debian-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-mate-arm64 zsh
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

## debian-mate-arm64.toml

```toml
[main]
name = "debian"
tag = ["mate", "2023-06-14"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-mate_arm64_2023-06-14_13-24.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "95b16a0fa26f5bf72b53f88a3ce8699655acf2eb21596955cf3322d0f20bf74e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4753995776

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1250402821

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230607"
previous_tag = "2023-06-07"
previous_file = "debian-mate_arm64_2023-06-07_13-16-rootfs.tar.zst"
previous_sha256 = "653794b833f65df1abd522ff4370c12751d920d5173c22e39103a6706ba6b696"

current_version = "latest01"
current_date = "20230614"
old_file = "debian-mate_arm64_2023-05-31_13-15-rootfs.tar.zst"
old_sha256 = "2b602a3fcd2917c30da15e12cc77fc3c9974fea91676346e2870fcb3403ba030"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-mate_arm64_2023-06-14_13-24-rootfs.tar.zst
# SHA256SUM=95b16a0fa26f5bf72b53f88a3ce8699655acf2eb21596955cf3322d0f20bf74e
# BUILD_DATE=20230614
# BUILD_TAG=2023-06-14
# STATUS=completed
# VERSION=latest01
# END_TIME=13:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-14
begin = 2023-06-14 12:22:29.033463686+00:00
start-sync_0 = 12:58:46
start-zstd = 13:04:44
start-sync_1 = 13:23:13
end-sync_1 = 13:24:39
end = 2023-06-14 13:24:39.233631533+00:00

[server]
repo = "cake233/debian-mate-arm64"

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
