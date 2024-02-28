# debian-zsh-386

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-386 \
    cake233/debian-zsh-386
```

## How to exec shell?

```sh
docker exec -it debian-zsh-386 zsh
```

## debian-zsh-386.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2024-02-28"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_i386_2024-02-28_12-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a2fb37ff239a03bdb3671930c743144c00829527af72ab1cfa01171156ef0b4b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "788M"
tar_bytes = 825548800

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "159M"
zstd_bytes = 165934922

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-zsh_i386_2023-11-22_12-15-rootfs.tar.zst"
previous_sha256 = "87fd9e4b978a2e6420c559c40ded9614ffa0d773bd1d1ca378522c856c964d81"

current_version = "latest01"
current_date = "20240228"
old_file = "debian-zsh_i386_2023-11-15_12-15-rootfs.tar.zst"
old_sha256 = "47e004f89a514836721806b9ae2d1197657c89d58a296ba1f44eb0e4a71c686b"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-zsh_i386_2024-02-28_12-16-rootfs.tar.zst
# SHA256SUM=a2fb37ff239a03bdb3671930c743144c00829527af72ab1cfa01171156ef0b4b
# BUILD_DATE=20240228
# BUILD_TAG=2024-02-28
# STATUS=completed
# VERSION=latest01
# END_TIME=12:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-28
begin = 2024-02-28 12:02:34.489692872+00:00
start-sync_0 = 12:12:20
start-zstd = 12:14:03
start-sync_1 = 12:16:17
end-sync_1 = 12:16:33
end = 2024-02-28 12:16:33.225398457+00:00

[server]
repo = "cake233/debian-zsh-386"

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
ldd = 'ldd (Debian GLIBC 2.37-15) 2.37'
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'
```
