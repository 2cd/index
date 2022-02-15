# fedora-kde-amd64

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
    --name fedora-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-kde-amd64 zsh
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

## fedora-kde-amd64.toml

```toml
[main]
name = "fedora"
tag = ["kde", "2022-02-15"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "fedora-kde_amd64_2022-02-15_13-31.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "bce7224161634a894a00ef008e3ec1255189b0e21a54c264a6e6791f08cad84e"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.4G"
tar_bytes = 4671224832

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1469433037

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220208"
previous_tag = "2022-02-08"
previous_file = "fedora-kde_amd64_2022-02-08_13-33-rootfs.tar.zst"
previous_sha256 = "f5052c70683bea196f86fcc0a7f14e73d0ae363e8546fa37fbdce02ee493ff74"

current_version = "latest01"
current_date = "20220215"
old_file = "fedora-kde_amd64_2022-02-01_13-07-rootfs.tar.zst"
old_sha256 = "deeddd39d6317aa0cd3ae9e6293b80cc1f188a57e0b5972c44be1a4a9310df16"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-kde_amd64_2022-02-15_13-31-rootfs.tar.zst
# SHA256SUM=bce7224161634a894a00ef008e3ec1255189b0e21a54c264a6e6791f08cad84e
# BUILD_DATE=20220215
# BUILD_TAG=2022-02-15
# STATUS=completed
# VERSION=latest01
# END_TIME=13:31

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-15
begin = 2022-02-15 13:02:46.037770235+00:00
start-sync_0 = 13:09:28
start-zstd = 13:14:35
start-sync_1 = 13:30:24
end-sync_1 = 13:31:58
end = 2022-02-15 13:31:58.433298574+00:00

[server]
repo = "cake233/fedora-kde-amd64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.8.1 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
