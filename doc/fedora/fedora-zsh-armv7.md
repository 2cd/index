# fedora-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name fedora-zsh-armv7 \
    cake233/fedora-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it fedora-zsh-armv7 zsh
```

## fedora-zsh-armv7.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2022-02-22"]
os = "fedora"
release = "rawhide"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "fedora-zsh_armhf_2022-02-22_12-21.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "10ad712358e3878ab5b8059df2d5e2e41921845189e4d2eae5042a90b75dc265"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "928M"
tar_bytes = 972405248

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "162M"
zstd_bytes = 169478362

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220215"
previous_tag = "2022-02-15"
previous_file = "fedora-zsh_armhf_2022-02-15_12-20-rootfs.tar.zst"
previous_sha256 = "a33c1ce11050446178612d62848cb8db4b1746847d48f7dfa65e02273ae65982"

current_version = "latest02"
current_date = "20220222"
old_file = "fedora-zsh_armhf_2022-02-08_12-19-rootfs.tar.zst"
old_sha256 = "d81fd35a44ba7bababcee0168ded3618c83c0545a49b8eba3a007b181c8b7728"
# edition 2021
# DISTRO_NAME=fedora-rawhide_armhf
# ROOTFS_FILE=fedora-zsh_armhf_2022-02-22_12-21-rootfs.tar.zst
# SHA256SUM=10ad712358e3878ab5b8059df2d5e2e41921845189e4d2eae5042a90b75dc265
# BUILD_DATE=20220222
# BUILD_TAG=2022-02-22
# STATUS=completed
# VERSION=latest02
# END_TIME=12:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-22
begin = 2022-02-22 12:02:30.360045256+00:00
start-sync_0 = 12:15:57
start-zstd = 12:17:55
start-sync_1 = 12:20:56
end-sync_1 = 12:21:10
end = 2022-02-22 12:21:10.714926519+00:00

[server]
repo = "cake233/fedora-zsh-armv7"

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
ldd = 'ldd (GNU libc) 2.34.9000'
zsh = 'zsh 5.8 (armv7hl-redhat-linux-gnu)'
```
