# arch-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-armv7 \
    cake233/arch-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it arch-zsh-armv7 zsh
```

## arch-zsh-armv7.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2022-02-23"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "arch-zsh_armhf_2022-02-23_00-27.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "3361dc1dceadecd81d4b2c6a7985f3b39f4e455f34933c5d346f99011fd57629"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "855M"
tar_bytes = 895512064

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "208M"
zstd_bytes = 218062023

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220209"
previous_tag = "2022-02-09"
previous_file = "arch-zsh_armhf_2022-02-09_00-35-rootfs.tar.zst"
previous_sha256 = "a6655ad20eaf2e14139fe810920007d5bd9c0600a7e2a8773ef42a65e7c53c98"

current_version = "latest01"
current_date = "20220223"
old_file = "arch-zsh_armhf_2022-02-02_00-34-rootfs.tar.zst"
old_sha256 = "9fe0eaaa5936439c4627c30e1c0ccd751a458d32a07447ec7799db90063694b2"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-zsh_armhf_2022-02-23_00-27-rootfs.tar.zst
# SHA256SUM=3361dc1dceadecd81d4b2c6a7985f3b39f4e455f34933c5d346f99011fd57629
# BUILD_DATE=20220223
# BUILD_TAG=2022-02-23
# STATUS=completed
# VERSION=latest01
# END_TIME=00:27

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-23
begin = 2022-02-23 00:05:51.477370880+00:00
start-sync_0 = 00:22:33
start-zstd = 00:24:09
start-sync_1 = 00:27:37
end-sync_1 = 00:27:54
end = 2022-02-23 00:27:54.501262273+00:00

[server]
repo = "cake233/arch-zsh-armv7"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.8.1 (armv7l-unknown-linux-gnueabihf)'
```
