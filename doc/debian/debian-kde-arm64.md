# debian-kde-arm64

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
    --name debian-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-kde-arm64 zsh
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

## debian-kde-arm64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2022-09-07"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_arm64_2022-09-07_13-49.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "25eec4f63dda4c9a479fd65ee27945d6ccabae1ac4ce3b2f2e172eb832f8f51f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.5G"
tar_bytes = 5802992128

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1646727647

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220831"
previous_tag = "2022-08-31"
previous_file = "debian-kde_arm64_2022-08-31_13-43-rootfs.tar.zst"
previous_sha256 = "44f2a7651d7ef082440c682c7000fceb18f51d16b2b57f92c2c6ecc90c6296b3"

current_version = "latest01"
current_date = "20220907"
old_file = "debian-kde_arm64_2022-08-24_13-40-rootfs.tar.zst"
old_sha256 = "66998aaf9d2e0b650ef63578ee28d1911e27af359c9e9c2ec810730c41763aa9"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2022-09-07_13-49-rootfs.tar.zst
# SHA256SUM=25eec4f63dda4c9a479fd65ee27945d6ccabae1ac4ce3b2f2e172eb832f8f51f
# BUILD_DATE=20220907
# BUILD_TAG=2022-09-07
# STATUS=completed
# VERSION=latest01
# END_TIME=13:49

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-07
begin = 2022-09-07 12:20:34.336306001+00:00
start-sync_0 = 13:16:57
start-zstd = 13:23:27
start-sync_1 = 13:47:32
end-sync_1 = 13:49:19
end = 2022-09-07 13:49:19.694521034+00:00

[server]
repo = "cake233/debian-kde-arm64"

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
ldd = 'ldd (Debian GLIBC 2.34-7) 2.34'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
