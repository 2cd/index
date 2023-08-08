# fedora-mate-amd64

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
    --name fedora-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-amd64 zsh
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

## fedora-mate-amd64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2023-08-08"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_amd64_2023-08-08_13-21.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ade4a1b48c397968d2a07de7662265fe8d2e340295a13f2f9e589448d6f632f4"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.0G"
tar_bytes = 5273236992

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1571351800

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230801"
previous_tag = "2023-08-01"
previous_file = "fedora-mate_amd64_2023-08-01_13-12-rootfs.tar.zst"
previous_sha256 = "0441f0e827e9e1c641bac27ed40d71196756a302356e7e985b55a40f6607b310"

current_version = "latest01"
current_date = "20230808"
old_file = "fedora-mate_amd64_2023-07-25_13-04-rootfs.tar.zst"
old_sha256 = "538bdcc215ce3c36fc1ad4bbbbed78780942b5bb7871c3b7b6df59ec1d5425af"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-mate_amd64_2023-08-08_13-21-rootfs.tar.zst
# SHA256SUM=ade4a1b48c397968d2a07de7662265fe8d2e340295a13f2f9e589448d6f632f4
# BUILD_DATE=20230808
# BUILD_TAG=2023-08-08
# STATUS=completed
# VERSION=latest01
# END_TIME=13:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-08
begin = 2023-08-08 12:44:33.844573471+00:00
start-sync_0 = 12:52:15
start-zstd = 12:57:10
start-sync_1 = 13:19:21
end-sync_1 = 13:21:27
end = 2023-08-08 13:21:27.322958990+00:00

[server]
repo = "cake233/fedora-mate-amd64"

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
ldd = 'ldd (GNU libc) 2.38'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
