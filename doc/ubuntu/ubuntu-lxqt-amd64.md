# ubuntu-lxqt-amd64

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
    --name ubuntu-lxqt-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-lxqt-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-lxqt-amd64 zsh
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

## ubuntu-lxqt-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2022-07-19", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_amd64_2022-07-19_00-58.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "cfaec42c74edb8fd5e4017cc8a9c1160ca519450454f12ebd11b76f429d3b63d"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3947627008

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1012M"
zstd_bytes = 1061027007

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220712"
previous_tag = "2022-07-12"
previous_file = "ubuntu-lxqt_amd64_2022-07-12_00-48-rootfs.tar.zst"
previous_sha256 = "4007190b696cce045821a3f3e7721897c7bebc3347c953911e9a6684daa63253"

current_version = "latest02"
current_date = "20220719"
old_file = "ubuntu-lxqt_amd64_2022-07-05_00-42-rootfs.tar.zst"
old_sha256 = "896499818927079e545db9b119ecc2080e3704a2647690d8d27af758d47f030d"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-lxqt_amd64_2022-07-19_00-58-rootfs.tar.zst
# SHA256SUM=cfaec42c74edb8fd5e4017cc8a9c1160ca519450454f12ebd11b76f429d3b63d
# BUILD_DATE=20220719
# BUILD_TAG=2022-07-19
# STATUS=completed
# VERSION=latest02
# END_TIME=00:58

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-19
begin = 2022-07-19 00:19:49.472708902+00:00
start-sync_0 = 00:34:10
start-zstd = 00:39:16
start-sync_1 = 00:56:46
end-sync_1 = 00:58:04
end = 2022-07-19 00:58:04.735652857+00:00

[server]
repo = "cake233/ubuntu-lxqt-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
