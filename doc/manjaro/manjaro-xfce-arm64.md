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
tag = ["xfce", "2023-09-01"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_arm64_2023-09-01_13-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1c14f34fd2a7481d5e90a3244bbbeaa55ef0373faa3e1affe3abbffb9faac112"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.3G"
tar_bytes = 4590190592

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1314761993

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230825"
previous_tag = "2023-08-25"
previous_file = "manjaro-xfce_arm64_2023-08-25_13-03-rootfs.tar.zst"
previous_sha256 = "680a8a47db4bc3a4f6ac4899930c6de89bad732ef57e831d7cee33df2989e672"

current_version = "latest01"
current_date = "20230901"
old_file = "manjaro-xfce_arm64_2023-08-18_13-17-rootfs.tar.zst"
old_sha256 = "dc4c963c1da26504dca7d029f3a56951700766a67ba57218cc9d24ccb1d91b3a"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-xfce_arm64_2023-09-01_13-05-rootfs.tar.zst
# SHA256SUM=1c14f34fd2a7481d5e90a3244bbbeaa55ef0373faa3e1affe3abbffb9faac112
# BUILD_DATE=20230901
# BUILD_TAG=2023-09-01
# STATUS=completed
# VERSION=latest01
# END_TIME=13:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-01
begin = 2023-09-01 12:25:59.587549780+00:00
start-sync_0 = 12:41:07
start-zstd = 12:45:00
start-sync_1 = 13:04:13
end-sync_1 = 13:05:43
end = 2023-09-01 13:05:43.084129667+00:00

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