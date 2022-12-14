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
tag = ["zsh", "2022-12-14"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_i386_2022-12-14_12-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "73a25e73b95e851861edd4b7aa5ba73430f9b7162d7235cdee865aad449b2543"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "770M"
tar_bytes = 806487552

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "151M"
zstd_bytes = 157298426

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221207"
previous_tag = "2022-12-07"
previous_file = "debian-zsh_i386_2022-12-07_12-18-rootfs.tar.zst"
previous_sha256 = "5dd2c1980b79911a368e366e15c5d45f2641eb6d4171639ab187ded35b9d8b94"

current_version = "latest01"
current_date = "20221214"
old_file = "debian-zsh_i386_2022-11-30_12-18-rootfs.tar.zst"
old_sha256 = "7131581246adb29844f88e1f21a0419f35f9c5c3e6b5ec42e189f36a1cf5d542"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-zsh_i386_2022-12-14_12-20-rootfs.tar.zst
# SHA256SUM=73a25e73b95e851861edd4b7aa5ba73430f9b7162d7235cdee865aad449b2543
# BUILD_DATE=20221214
# BUILD_TAG=2022-12-14
# STATUS=completed
# VERSION=latest01
# END_TIME=12:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-14
begin = 2022-12-14 12:02:24.591695121+00:00
start-sync_0 = 12:15:55
start-zstd = 12:17:44
start-sync_1 = 12:20:38
end-sync_1 = 12:20:53
end = 2022-12-14 12:20:53.696137459+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-6) 2.36'
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'
```
