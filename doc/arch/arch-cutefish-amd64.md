# arch-cutefish-amd64

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
    --name arch-cutefish-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-cutefish-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-cutefish-amd64 zsh
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

## arch-cutefish-amd64.toml

```toml
[main]
name = "arch"
tag = ["cutefish", "2022-07-20"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-cutefish_amd64_2022-07-20_01-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c567006434c688bdfb6117e7cf45b03256dbff1ca5d86470354a7165c41c83a1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.9G"
tar_bytes = 4130434560

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1172242954

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220713"
previous_tag = "2022-07-13"
previous_file = "arch-cutefish_amd64_2022-07-13_01-02-rootfs.tar.zst"
previous_sha256 = "2d19f8aa6580f5275835887f414fc2cdc582315197d5bcb6d6136a5f8983b3f5"

current_version = "latest01"
current_date = "20220720"
old_file = "arch-cutefish_amd64_2022-07-06_00-52-rootfs.tar.zst"
old_sha256 = "54a90ded1b527900b0063ac537981d1403a96045d43468ef73c67ebe9d26828f"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-cutefish_amd64_2022-07-20_01-20-rootfs.tar.zst
# SHA256SUM=c567006434c688bdfb6117e7cf45b03256dbff1ca5d86470354a7165c41c83a1
# BUILD_DATE=20220720
# BUILD_TAG=2022-07-20
# STATUS=completed
# VERSION=latest01
# END_TIME=01:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-20
begin = 2022-07-20 00:53:48.873865958+00:00
start-sync_0 = 00:59:36
start-zstd = 01:04:18
start-sync_1 = 01:19:19
end-sync_1 = 01:20:34
end = 2022-07-20 01:20:34.082444126+00:00

[server]
repo = "cake233/arch-cutefish-amd64"

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
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
