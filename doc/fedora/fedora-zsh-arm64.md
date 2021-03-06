# fedora-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name fedora-zsh-arm64 \
    cake233/fedora-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it fedora-zsh-arm64 zsh
```

## fedora-zsh-arm64.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2022-07-19"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_arm64_2022-07-19_12-42.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4654b807891aef9c4e454777e138c1ab31fb31802468326df7bc5d07245eb2b6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1124411392

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "174M"
zstd_bytes = 182247410

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220712"
previous_tag = "2022-07-12"
previous_file = "fedora-zsh_arm64_2022-07-12_12-42-rootfs.tar.zst"
previous_sha256 = "b1d14d840fbd9497526a3de37ed28fe8f5ee2a211655f35959f5fe262e5d03d8"

current_version = "latest01"
current_date = "20220719"
old_file = "fedora-zsh_arm64_2022-07-05_12-42-rootfs.tar.zst"
old_sha256 = "16a5f227e7d5cdcea901cd2aa0ff4cda0845bc5cdd972bf93bd88a671c26af27"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2022-07-19_12-42-rootfs.tar.zst
# SHA256SUM=4654b807891aef9c4e454777e138c1ab31fb31802468326df7bc5d07245eb2b6
# BUILD_DATE=20220719
# BUILD_TAG=2022-07-19
# STATUS=completed
# VERSION=latest01
# END_TIME=12:42

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-19
begin = 2022-07-19 12:02:32.223505764+00:00
start-sync_0 = 12:36:30
start-zstd = 12:38:30
start-sync_1 = 12:41:42
end-sync_1 = 12:42:01
end = 2022-07-19 12:42:01.857689768+00:00

[server]
repo = "cake233/fedora-zsh-arm64"

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'
```
