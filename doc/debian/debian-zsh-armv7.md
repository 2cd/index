# debian-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-armv7 \
    cake233/debian-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it debian-zsh-armv7 zsh
```

## debian-zsh-armv7.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2023-09-20"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_armhf_2023-09-20_12-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6afe716ab249ce0311b17f51884b02c5f965e0978310a31a6a685deb60ae59f6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "700M"
tar_bytes = 733664768

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "145M"
zstd_bytes = 151061771

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230913"
previous_tag = "2023-09-13"
previous_file = "debian-zsh_armhf_2023-09-13_12-23-rootfs.tar.zst"
previous_sha256 = "c01fad5f27da20b794c92e275e3e13aeee74b0a96ec0d8edfff25d0efc2d0971"

current_version = "latest02"
current_date = "20230920"
old_file = "debian-zsh_armhf_2023-09-06_12-21-rootfs.tar.zst"
old_sha256 = "40da9f13af24a4f6bd84865f1de56e703edcc3423cd94d4772cedcc9f2684a0b"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-zsh_armhf_2023-09-20_12-20-rootfs.tar.zst
# SHA256SUM=6afe716ab249ce0311b17f51884b02c5f965e0978310a31a6a685deb60ae59f6
# BUILD_DATE=20230920
# BUILD_TAG=2023-09-20
# STATUS=completed
# VERSION=latest02
# END_TIME=12:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-20
begin = 2023-09-20 12:02:34.545595738+00:00
start-sync_0 = 12:15:33
start-zstd = 12:17:18
start-sync_1 = 12:19:52
end-sync_1 = 12:20:08
end = 2023-09-20 12:20:08.060132640+00:00

[server]
repo = "cake233/debian-zsh-armv7"

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
ldd = 'ldd (Debian GLIBC 2.37-10) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```
