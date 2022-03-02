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
tag = ["zsh", "2022-03-02"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
x11_or_wayland = false

[file]
name = "debian-zsh_i386_2022-03-02_12-21.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "72c3a4afce5655c39e68577d81932e1a0e9fb8feb197b982e18a98b478f6c106"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "748M"
tar_bytes = 783515136

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "147M"
zstd_bytes = 153322877

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220223"
previous_tag = "2022-02-23"
previous_file = "debian-zsh_i386_2022-02-23_12-20-rootfs.tar.zst"
previous_sha256 = "c19dc10966f1f5520e79d9d15a7037657f4daf0c49eb13c850a4a86693b97bee"

current_version = "latest01"
current_date = "20220302"
old_file = "debian-zsh_i386_2022-02-16_12-23-rootfs.tar.zst"
old_sha256 = "ac477f104a268a24ee15d4fed6be49685b86b5ff8fb5f2b9e48a7b222c5d7a8a"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-zsh_i386_2022-03-02_12-21-rootfs.tar.zst
# SHA256SUM=72c3a4afce5655c39e68577d81932e1a0e9fb8feb197b982e18a98b478f6c106
# BUILD_DATE=20220302
# BUILD_TAG=2022-03-02
# STATUS=completed
# VERSION=latest01
# END_TIME=12:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-02
begin = 2022-03-02 12:02:29.330496555+00:00
start-sync_0 = 12:16:10
start-zstd = 12:18:08
start-sync_1 = 12:20:43
end-sync_1 = 12:21:03
end = 2022-03-02 12:21:03.539742763+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.8.1 (i686-debian-linux-gnu)'
```
