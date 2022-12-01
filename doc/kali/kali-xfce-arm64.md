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
tag = ["xfce", "2022-12-01"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_arm64_2022-12-01_13-38.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f4dd58044eff11c806b5b4e44be76ee61ec64b53dd6288e2a9db344cd110edd9"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4842188288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1373776179

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221124"
previous_tag = "2022-11-24"
previous_file = "kali-xfce_arm64_2022-11-24_13-22-rootfs.tar.zst"
previous_sha256 = "8970a1220daee6d47ffbd99b5163bf65efb0cd8f29f8c9692a1cec2bec361d54"

current_version = "latest01"
current_date = "20221201"
old_file = "kali-xfce_arm64_2022-11-17_13-23-rootfs.tar.zst"
old_sha256 = "54943951630401cd752c8ac5585486ae31a39332e7e8111d7cef623f96e37a1f"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2022-12-01_13-38-rootfs.tar.zst
# SHA256SUM=f4dd58044eff11c806b5b4e44be76ee61ec64b53dd6288e2a9db344cd110edd9
# BUILD_DATE=20221201
# BUILD_TAG=2022-12-01
# STATUS=completed
# VERSION=latest01
# END_TIME=13:38

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-01
begin = 2022-12-01 12:19:20.945027232+00:00
start-sync_0 = 13:14:30
start-zstd = 13:19:13
start-sync_1 = 13:37:04
end-sync_1 = 13:38:31
end = 2022-12-01 13:38:31.475546295+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-4) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
