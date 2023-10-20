# manjaro-xfce-arm64

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
    --name manjaro-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/manjaro-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it manjaro-xfce-arm64 zsh
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

## manjaro-xfce-arm64.toml

```toml
[main]
name = "manjaro"
tag = ["xfce", "2023-10-20"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_arm64_2023-10-20_13-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "344f49290228e5885775fee817a9107c97d788b0decedf369965a359478d3a67"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.4G"
tar_bytes = 4657227776

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1319461249

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231013"
previous_tag = "2023-10-13"
previous_file = "manjaro-xfce_arm64_2023-10-13_12-57-rootfs.tar.zst"
previous_sha256 = "766c318ab43b31d4e1cb17f110a8b866053cf6bfef61e2c14d2a3bc3746afc39"

current_version = "latest02"
current_date = "20231020"
old_file = "manjaro-xfce_arm64_2023-10-06_12-57-rootfs.tar.zst"
old_sha256 = "d3073793915bf6a57c23088a2046164ebad6da8412e538ea78ae45573624cfbb"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-xfce_arm64_2023-10-20_13-12-rootfs.tar.zst
# SHA256SUM=344f49290228e5885775fee817a9107c97d788b0decedf369965a359478d3a67
# BUILD_DATE=20231020
# BUILD_TAG=2023-10-20
# STATUS=completed
# VERSION=latest02
# END_TIME=13:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-20
begin = 2023-10-20 12:25:07.425008637+00:00
start-sync_0 = 12:42:20
start-zstd = 12:47:43
start-sync_1 = 13:11:00
end-sync_1 = 13:12:53
end = 2023-10-20 13:12:53.285444741+00:00

[server]
repo = "cake233/manjaro-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
