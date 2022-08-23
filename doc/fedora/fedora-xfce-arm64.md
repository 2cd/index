# fedora-xfce-arm64

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
    --name fedora-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-xfce-arm64 zsh
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

## fedora-xfce-arm64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2022-08-23"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_arm64_2022-08-23_14-33.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8a45ce73a3d9497783299f66f0cb54386fc161842c710a935bee52c1b76d2413"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.3G"
tar_bytes = 5678398976

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1617275066

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220816"
previous_tag = "2022-08-16"
previous_file = "fedora-xfce_arm64_2022-08-16_14-32-rootfs.tar.zst"
previous_sha256 = "f9b5af64df392971aabfdb1b48b3cd0c631334afe7639637b0521a774f881ae2"

current_version = "latest01"
current_date = "20220823"
old_file = "fedora-xfce_arm64_2022-08-09_14-19-rootfs.tar.zst"
old_sha256 = "1a4e185fa02e2bdd1034b6166715b4983f8346c743a65d99df672e92c68e5f1e"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-xfce_arm64_2022-08-23_14-33-rootfs.tar.zst
# SHA256SUM=8a45ce73a3d9497783299f66f0cb54386fc161842c710a935bee52c1b76d2413
# BUILD_DATE=20220823
# BUILD_TAG=2022-08-23
# STATUS=completed
# VERSION=latest01
# END_TIME=14:33

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-23
begin = 2022-08-23 12:48:27.722304297+00:00
start-sync_0 = 14:06:08
start-zstd = 14:11:39
start-sync_1 = 14:31:31
end-sync_1 = 14:33:27
end = 2022-08-23 14:33:27.567356984+00:00

[server]
repo = "cake233/fedora-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
