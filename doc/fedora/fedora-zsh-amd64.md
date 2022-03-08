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
tag = ["zsh", "2022-03-08"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "fedora-zsh_amd64_2022-03-08_12-10.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "000fb61da73009201b84edc1ec897163400106ccda4a33f4ffb6df7d5b210ae5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "964M"
tar_bytes = 1010082304

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "166M"
zstd_bytes = 173047552

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220301"
previous_tag = "2022-03-01"
previous_file = "fedora-zsh_amd64_2022-03-01_12-09-rootfs.tar.zst"
previous_sha256 = "b73a85bb2c0ff910a275c4e77c02f50d019b1c214e8b48cea5c8f181cb4f277c"

current_version = "latest02"
current_date = "20220308"
old_file = "fedora-zsh_amd64_2022-02-22_12-10-rootfs.tar.zst"
old_sha256 = "9c6c6623a1b46efa1d23b1687160b84dbb09fad4f378d5bc9e28f65009c90dc3"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2022-03-08_12-10-rootfs.tar.zst
# SHA256SUM=000fb61da73009201b84edc1ec897163400106ccda4a33f4ffb6df7d5b210ae5
# BUILD_DATE=20220308
# BUILD_TAG=2022-03-08
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-08
begin = 2022-03-08 12:02:32.098588307+00:00
start-sync_0 = 12:04:32
start-zstd = 12:06:38
start-sync_1 = 12:10:23
end-sync_1 = 12:10:38
end = 2022-03-08 12:10:38.694344887+00:00

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.8.1 (x86_64-redhat-linux-gnu)'
```
