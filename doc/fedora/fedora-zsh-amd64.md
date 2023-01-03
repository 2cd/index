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
tag = ["zsh", "2023-01-03"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_amd64_2023-01-03_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4ca687fe24ec0cbb45415ac42c14cdf5523525162e889c9df289aeb4cb37106e"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1324927488

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "221M"
zstd_bytes = 231071264

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221227"
previous_tag = "2022-12-27"
previous_file = "fedora-zsh_amd64_2022-12-27_12-11-rootfs.tar.zst"
previous_sha256 = "26f6768d6e42d768175da1deb6ace1335f89f5d1c5ea986e531e8325dd78cdbf"

current_version = "latest02"
current_date = "20230103"
old_file = "fedora-zsh_amd64_2022-12-20_12-10-rootfs.tar.zst"
old_sha256 = "599233db99de5ea48793d760116e46ca3f62a3d0444454cb21bf7148572fb8e8"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2023-01-03_12-10-rootfs.tar.zst
# SHA256SUM=4ca687fe24ec0cbb45415ac42c14cdf5523525162e889c9df289aeb4cb37106e
# BUILD_DATE=20230103
# BUILD_TAG=2023-01-03
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-03
begin = 2023-01-03 12:02:26.350050327+00:00
start-sync_0 = 12:04:21
start-zstd = 12:06:17
start-sync_1 = 12:10:05
end-sync_1 = 12:10:22
end = 2023-01-03 12:10:22.916838991+00:00

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
