# debian-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-amd64 \
    cake233/debian-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it debian-zsh-amd64 zsh
```

## debian-zsh-amd64.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2022-12-28"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_amd64_2022-12-28_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "36070055e663ee9faf2324742d20e154392dd25e672768899c3109d2619a1031"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "765M"
tar_bytes = 801705984

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "147M"
zstd_bytes = 153925005

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221221"
previous_tag = "2022-12-21"
previous_file = "debian-zsh_amd64_2022-12-21_12-08-rootfs.tar.zst"
previous_sha256 = "672bb8c5457512ddc58e342485493c6c7517f2d1a7042ea02ce1538384e4db31"

current_version = "latest01"
current_date = "20221228"
old_file = "debian-zsh_amd64_2022-12-14_12-08-rootfs.tar.zst"
old_sha256 = "1d4627ff990ad67387a33120262028c88cde7eb05849d638f2ed249d2cfca293"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-zsh_amd64_2022-12-28_12-08-rootfs.tar.zst
# SHA256SUM=36070055e663ee9faf2324742d20e154392dd25e672768899c3109d2619a1031
# BUILD_DATE=20221228
# BUILD_TAG=2022-12-28
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-28
begin = 2022-12-28 12:02:25.892527223+00:00
start-sync_0 = 12:04:17
start-zstd = 12:06:06
start-sync_1 = 12:08:43
end-sync_1 = 12:08:59
end = 2022-12-28 12:08:59.230883994+00:00

[server]
repo = "cake233/debian-zsh-amd64"

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
ldd = 'ldd (Debian GLIBC 2.36-7) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
