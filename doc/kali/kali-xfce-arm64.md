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
tag = ["xfce", "2023-01-19"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_arm64_2023-01-19_13-41.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5ff5440097326cfcb762e9423ae52aa7a1c1c6cb119a5fc9a39ad642c1e912b6"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.7G"
tar_bytes = 4967571968

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1385685692

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230112"
previous_tag = "2023-01-12"
previous_file = "kali-xfce_arm64_2023-01-12_13-40-rootfs.tar.zst"
previous_sha256 = "4e55c99ad9f15946f919d645fbd8729813dfddaff77e26d8978a690b062d341e"

current_version = "latest02"
current_date = "20230119"
old_file = "kali-xfce_arm64_2023-01-05_13-47-rootfs.tar.zst"
old_sha256 = "99443a54c9410dc95bb7bf3fce5e6b951f3df43daff07c96c2353c6836547144"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2023-01-19_13-41-rootfs.tar.zst
# SHA256SUM=5ff5440097326cfcb762e9423ae52aa7a1c1c6cb119a5fc9a39ad642c1e912b6
# BUILD_DATE=20230119
# BUILD_TAG=2023-01-19
# STATUS=completed
# VERSION=latest02
# END_TIME=13:41

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-19
begin = 2023-01-19 12:25:07.072909931+00:00
start-sync_0 = 13:18:35
start-zstd = 13:23:02
start-sync_1 = 13:40:29
end-sync_1 = 13:41:59
end = 2023-01-19 13:41:59.732585024+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-6) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
