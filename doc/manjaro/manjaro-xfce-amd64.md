# manjaro-xfce-amd64

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
    --name manjaro-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/manjaro-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it manjaro-xfce-amd64 zsh
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

## manjaro-xfce-amd64.toml

```toml
[main]
name = "manjaro"
tag = ["xfce", "2023-03-17"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_amd64_2023-03-17_12-46.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0f3fdf33bb4540dfbfc4d3876e019eb7519b360e047f054fe0ca89d86dc06c18"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 3985900544

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1176512002

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230310"
previous_tag = "2023-03-10"
previous_file = "manjaro-xfce_amd64_2023-03-10_12-41-rootfs.tar.zst"
previous_sha256 = "8c0fe642a2db1a4c5b7a76b860be36f1f55a9efe02115b1bf9805dd7f1f3cdbd"

current_version = "latest01"
current_date = "20230317"
old_file = "manjaro-xfce_amd64_2023-03-03_12-43-rootfs.tar.zst"
old_sha256 = "492cdd69be248975faf3b398891ad620bba001e323faf765a3b30e8a1f33570c"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-xfce_amd64_2023-03-17_12-46-rootfs.tar.zst
# SHA256SUM=0f3fdf33bb4540dfbfc4d3876e019eb7519b360e047f054fe0ca89d86dc06c18
# BUILD_DATE=20230317
# BUILD_TAG=2023-03-17
# STATUS=completed
# VERSION=latest01
# END_TIME=12:46

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-17
begin = 2023-03-17 12:20:08.921584459+00:00
start-sync_0 = 12:25:08
start-zstd = 12:28:37
start-sync_1 = 12:45:35
end-sync_1 = 12:46:51
end = 2023-03-17 12:46:51.266470936+00:00

[server]
repo = "cake233/manjaro-xfce-amd64"

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
