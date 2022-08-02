# fedora-xfce-arm64

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
    --name fedora-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-xfce-arm64 zsh
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

## fedora-xfce-arm64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2022-08-02"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_arm64_2022-08-02_14-25.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e62873be4ff30b44fe658387b1886fb17bc136bbd4596df70c034a221adcacc7"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.2G"
tar_bytes = 5507314176

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1539971567

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220712"
previous_tag = "2022-07-12"
previous_file = "fedora-xfce_arm64_2022-07-12_14-27-rootfs.tar.zst"
previous_sha256 = "597406477094fda5a0afe140523f2a6b86a1025456b5f0044e8f112b365a3f70"

current_version = "latest01"
current_date = "20220802"
old_file = "fedora-xfce_arm64_2022-07-05_14-37-rootfs.tar.zst"
old_sha256 = "19524144a1a1e2a56814e7d181ca88eeb959dcd4eaee298b70be1eedb0c1244d"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-xfce_arm64_2022-08-02_14-25-rootfs.tar.zst
# SHA256SUM=e62873be4ff30b44fe658387b1886fb17bc136bbd4596df70c034a221adcacc7
# BUILD_DATE=20220802
# BUILD_TAG=2022-08-02
# STATUS=completed
# VERSION=latest01
# END_TIME=14:25

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-02
begin = 2022-08-02 12:50:14.013137904+00:00
start-sync_0 = 14:01:07
start-zstd = 14:05:35
start-sync_1 = 14:23:32
end-sync_1 = 14:25:03
end = 2022-08-02 14:25:03.350516937+00:00

[server]
repo = "cake233/fedora-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
