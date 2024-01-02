# fedora-kde-arm64

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
    --name fedora-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-kde-arm64 zsh
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

## fedora-kde-arm64.toml

```toml
[main]
name = "fedora"
tag = ["kde", "2024-01-02"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_arm64_2024-01-02_14-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "df3b82059796de78b9748efe474ca0b92254b1c9bde072559bca4942491ecdaf"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "7.4G"
tar_bytes = 7857832448

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.9G"
zstd_bytes = 2012177125

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231121"
previous_tag = "2023-11-21"
previous_file = "fedora-kde_arm64_2023-11-21_14-34-rootfs.tar.zst"
previous_sha256 = "786e794664181e84ad0ad1d81dca9e902337e5225297c15d5286056c81b28e52"

current_version = "latest02"
current_date = "20240102"
old_file = "fedora-kde_arm64_2023-11-14_14-54-rootfs.tar.zst"
old_sha256 = "2edaeb92d54b15cad99788d421609db146688f042dd18c0bd4003d758e13cbf5"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-kde_arm64_2024-01-02_14-26-rootfs.tar.zst
# SHA256SUM=df3b82059796de78b9748efe474ca0b92254b1c9bde072559bca4942491ecdaf
# BUILD_DATE=20240102
# BUILD_TAG=2024-01-02
# STATUS=completed
# VERSION=latest02
# END_TIME=14:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-02
begin = 2024-01-02 12:38:25.125930644+00:00
start-sync_0 = 14:03:56
start-zstd = 14:07:33
start-sync_1 = 14:25:20
end-sync_1 = 14:26:41
end = 2024-01-02 14:26:41.524956731+00:00

[server]
repo = "cake233/fedora-kde-arm64"

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
ldd = 'ldd (GNU libc) 2.38.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
