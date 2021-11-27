# arch-xfce-amd64

## How to run it?

```shell
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
    --name arch-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-amd64
```

## How to start vnc?

```shell
    docker exex -it arch-xfce-amd64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```shell
    startvnc
```

or

```shell
    startx11vnc
```

or

```shell
    novnc
```

Note:

If you want to use novnc, then open your browser, and type the address:

```
localhost:36081
```

If you want to use tiger/x11vnc, then open vnc viewer, then type the address:

```
localhost:5903
```

## build info

```toml
[main]
name = "arch"
tag = ["xfce", "2021-11-27"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
nogui = false

# If the value is false, then the container will not be downloaded.
completed = true

[file]
name = "arch-xfce-amd64_2021-11-27_17-11.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "c47518180714b942c639d7edf565c5cc482e34495bfbe72c4b5bab48fb0bd0c1"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar-bytes = 3833744384

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd-bytes = 1275142703

[compatibility]
compatible_mode = true
rootfs_version = "latest01"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-xfce-amd64_2021-11-27_17-11.tar.zst
# BUILD_DATE=20211127
# STATUS=completed
# VERSION=latest01
# END_TIME=17:11

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-27 16:50:37.256725764+00:00
start-sync_0 = 17:02:09
start-zstd = 17:06:11
start-sync_1 = 17:10:01
end-sync_1 = 17:11:34
end = 2021-11-27 17:11:34.926195770+00:00

[server]
name = "docker"
node = 4
repo = "cake233/arch-xfce-amd64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
