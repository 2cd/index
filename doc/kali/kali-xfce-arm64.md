# kali-xfce-arm64

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
    --name kali-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-arm64 zsh
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

## kali-xfce-arm64.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2023-07-13"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_arm64_2023-07-13_13-41.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f65978de9044df1dd32430b77f3e8081868e856de953ee74bf484dd6be7cd6db"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.9G"
tar_bytes = 5237507072

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1441937625

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230706"
previous_tag = "2023-07-06"
previous_file = "kali-xfce_arm64_2023-07-06_13-48-rootfs.tar.zst"
previous_sha256 = "cdc8aca2eaf8c320d9b6dbdc77fe8ad2f2786fbf868fee569ad85c0f5f64cbea"

current_version = "latest02"
current_date = "20230713"
old_file = "kali-xfce_arm64_2023-06-29_13-29-rootfs.tar.zst"
old_sha256 = "96dcfa24f1990e4d4782fa2d1bc76c222495fe307d14685bbaef985aa7ef6471"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2023-07-13_13-41-rootfs.tar.zst
# SHA256SUM=f65978de9044df1dd32430b77f3e8081868e856de953ee74bf484dd6be7cd6db
# BUILD_DATE=20230713
# BUILD_TAG=2023-07-13
# STATUS=completed
# VERSION=latest02
# END_TIME=13:41

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-13
begin = 2023-07-13 12:25:38.762487532+00:00
start-sync_0 = 13:13:42
start-zstd = 13:18:40
start-sync_1 = 13:40:00
end-sync_1 = 13:41:33
end = 2023-07-13 13:41:33.057976634+00:00

[server]
repo = "cake233/kali-xfce-arm64"

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
