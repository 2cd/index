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
tag = ["zsh", "2023-01-31"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_amd64_2023-01-31_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e1cd55f26a534fc1b9c0de1f1ffb875d3a326f81b475b9e6bca098c1c2384450"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1325923328

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "223M"
zstd_bytes = 233750678

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230124"
previous_tag = "2023-01-24"
previous_file = "fedora-zsh_amd64_2023-01-24_12-12-rootfs.tar.zst"
previous_sha256 = "848ca82b08e37912d478c14c80c552da182adb0faa5ee41df576e772699dd202"

current_version = "latest02"
current_date = "20230131"
old_file = "fedora-zsh_amd64_2023-01-17_12-12-rootfs.tar.zst"
old_sha256 = "414e701195dd404eb19e7cf8d87f61458b4ea5f8d6efa6269bfcea2ef76dedad"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2023-01-31_12-11-rootfs.tar.zst
# SHA256SUM=e1cd55f26a534fc1b9c0de1f1ffb875d3a326f81b475b9e6bca098c1c2384450
# BUILD_DATE=20230131
# BUILD_TAG=2023-01-31
# STATUS=completed
# VERSION=latest02
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-31
begin = 2023-01-31 12:02:26.057980744+00:00
start-sync_0 = 12:04:39
start-zstd = 12:06:42
start-sync_1 = 12:10:44
end-sync_1 = 12:11:04
end = 2023-01-31 12:11:04.095565642+00:00

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
