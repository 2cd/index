# arch-cutefish-arm64

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
    --name arch-cutefish-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-cutefish-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-cutefish-arm64 zsh
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

## arch-cutefish-arm64.toml

```toml
[main]
name = "arch"
tag = ["cutefish", "2022-03-09"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "arch-cutefish_arm64_2022-03-09_01-02.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "a63e91aa37a1504c7f4dac709313e7dd6734e93f6abcf69f2084267fb0a1af06"

# zstd: [1-22]
zstd-level = 15

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.4G"
tar_bytes = 4683592704

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1404036659

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220303"
previous_tag = "2022-03-03"
previous_file = "arch-cutefish_arm64_2022-03-03_16-57-rootfs.tar.zst"
previous_sha256 = "646c937a799e727a41b7ccd85753ec924ebdec0f6297549eafaa18d67820553f"

current_version = "latest02"
current_date = "20220309"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-cutefish_arm64_2022-03-09_01-02-rootfs.tar.zst
# SHA256SUM=a63e91aa37a1504c7f4dac709313e7dd6734e93f6abcf69f2084267fb0a1af06
# BUILD_DATE=20220309
# BUILD_TAG=2022-03-09
# STATUS=completed
# VERSION=latest02
# END_TIME=01:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-09
begin = 2022-03-09 00:34:38.763138330+00:00
start-sync_0 = 00:50:24
start-zstd = 00:54:23
start-sync_1 = 01:01:14
end-sync_1 = 01:02:37
end = 2022-03-09 01:02:37.153999198+00:00

[server]
repo = "cake233/arch-cutefish-arm64"

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
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
