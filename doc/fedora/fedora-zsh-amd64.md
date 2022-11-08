# fedora-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name fedora-zsh-amd64 \
    cake233/fedora-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it fedora-zsh-amd64 zsh
```

## fedora-zsh-amd64.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2022-11-08"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_amd64_2022-11-08_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c7cb1580b6f28c9561a9b26964ad2cbcf86adf112ce5952067aa185899f1aeff"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1322369024

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "221M"
zstd_bytes = 231488775

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221101"
previous_tag = "2022-11-01"
previous_file = "fedora-zsh_amd64_2022-11-01_12-12-rootfs.tar.zst"
previous_sha256 = "9d3e07a3b723f2c2d1c548e702e776fb5ffde23379799751f590269c7416b118"

current_version = "latest02"
current_date = "20221108"
old_file = "fedora-zsh_amd64_2022-10-25_12-10-rootfs.tar.zst"
old_sha256 = "3d2353cfdfd2142710952d6b9cd98a3af84f024072fe2f77e8c83e66dad39224"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2022-11-08_12-11-rootfs.tar.zst
# SHA256SUM=c7cb1580b6f28c9561a9b26964ad2cbcf86adf112ce5952067aa185899f1aeff
# BUILD_DATE=20221108
# BUILD_TAG=2022-11-08
# STATUS=completed
# VERSION=latest02
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-08
begin = 2022-11-08 12:02:23.190928187+00:00
start-sync_0 = 12:04:16
start-zstd = 12:06:23
start-sync_1 = 12:10:47
end-sync_1 = 12:11:06
end = 2022-11-08 12:11:06.537315405+00:00

[server]
repo = "cake233/fedora-zsh-amd64"

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'
```
