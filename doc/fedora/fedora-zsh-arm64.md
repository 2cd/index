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
tag = ["zsh", "2023-02-21"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_arm64_2023-02-21_12-55.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f365f5830922b9056ffccbc1619ce9ea72d61b8a9388236c546f7c72e6547113"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1525735424

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "216M"
zstd_bytes = 225775010

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230214"
previous_tag = "2023-02-14"
previous_file = "fedora-zsh_arm64_2023-02-14_12-54-rootfs.tar.zst"
previous_sha256 = "93f3d8d8b62001595ba17a79e5057fb5225b1425429edca0862bd073d6a50b43"

current_version = "latest01"
current_date = "20230221"
old_file = "fedora-zsh_arm64_2023-02-07_13-04-rootfs.tar.zst"
old_sha256 = "6810876bf103746d549dadaf66f43fec571632af8a8393c530bdcd9e625d1a40"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2023-02-21_12-55-rootfs.tar.zst
# SHA256SUM=f365f5830922b9056ffccbc1619ce9ea72d61b8a9388236c546f7c72e6547113
# BUILD_DATE=20230221
# BUILD_TAG=2023-02-21
# STATUS=completed
# VERSION=latest01
# END_TIME=12:55

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-21
begin = 2023-02-21 12:02:30.487339227+00:00
start-sync_0 = 12:49:19
start-zstd = 12:51:27
start-sync_1 = 12:55:34
end-sync_1 = 12:55:52
end = 2023-02-21 12:55:52.762248885+00:00

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'
```
