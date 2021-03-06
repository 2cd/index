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
tag = ["zsh", "2022-03-15"]
os = "fedora"
release = "rawhide"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "fedora-zsh_armhf_2022-03-15_12-21.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "1248bbc5545c06a11a6c02a4b4c567a9fb1b67d0077170566b07476c14afb1ac"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "928M"
tar_bytes = 972486144

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "162M"
zstd_bytes = 169495523

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220308"
previous_tag = "2022-03-08"
previous_file = "fedora-zsh_armhf_2022-03-08_12-24-rootfs.tar.zst"
previous_sha256 = "a658706c1409947eb73f45cc3bc469883cb0324dae26cfc78050b0769393ee67"

current_version = "latest01"
current_date = "20220315"
old_file = "fedora-zsh_armhf_2022-03-01_12-23-rootfs.tar.zst"
old_sha256 = "52b88d8885a52d7b08b22be432842ba0ca7ec3595fa536439e71acacd9753301"
# edition 2021
# DISTRO_NAME=fedora-rawhide_armhf
# ROOTFS_FILE=fedora-zsh_armhf_2022-03-15_12-21-rootfs.tar.zst
# SHA256SUM=1248bbc5545c06a11a6c02a4b4c567a9fb1b67d0077170566b07476c14afb1ac
# BUILD_DATE=20220315
# BUILD_TAG=2022-03-15
# STATUS=completed
# VERSION=latest01
# END_TIME=12:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-15
begin = 2022-03-15 12:02:28.558687541+00:00
start-sync_0 = 12:16:12
start-zstd = 12:18:08
start-sync_1 = 12:20:57
end-sync_1 = 12:21:13
end = 2022-03-15 12:21:13.630343203+00:00

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
