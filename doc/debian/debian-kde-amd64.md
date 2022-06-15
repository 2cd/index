# debian-kde-amd64

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
    --name debian-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-kde-amd64 zsh
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

## debian-kde-amd64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2022-06-15"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_amd64_2022-06-15_12-47.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "41fd42a63bb2fcc047d637d404eb473d7bffac176abf3b4537d307d9658a3523"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.8G"
tar_bytes = 5058022400

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1468144705

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220608"
previous_tag = "2022-06-08"
previous_file = "debian-kde_amd64_2022-06-08_12-58-rootfs.tar.zst"
previous_sha256 = "7bd570d49b5fe307a110d45982aee9edbe02cffe9a7f97c1a251efb361ee9bc2"

current_version = "latest02"
current_date = "20220615"
old_file = "debian-kde_amd64_2022-06-01_13-01-rootfs.tar.zst"
old_sha256 = "386f212e95ce41c0c0354a922398171074e935f22e377869dc33691dfb242713"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-kde_amd64_2022-06-15_12-47-rootfs.tar.zst
# SHA256SUM=41fd42a63bb2fcc047d637d404eb473d7bffac176abf3b4537d307d9658a3523
# BUILD_DATE=20220615
# BUILD_TAG=2022-06-15
# STATUS=completed
# VERSION=latest02
# END_TIME=12:47

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-15
begin = 2022-06-15 12:19:17.483322068+00:00
start-sync_0 = 12:25:17
start-zstd = 12:29:36
start-sync_1 = 12:46:00
end-sync_1 = 12:47:31
end = 2022-06-15 12:47:31.249334134+00:00

[server]
repo = "cake233/debian-kde-amd64"

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
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
