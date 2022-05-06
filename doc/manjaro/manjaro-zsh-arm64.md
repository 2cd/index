# manjaro-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name manjaro-zsh-arm64 \
    cake233/manjaro-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it manjaro-zsh-arm64 zsh
```

## manjaro-zsh-arm64.toml

```toml
[main]
name = "manjaro"
tag = ["zsh", "2022-05-06"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_arm64_2022-05-06_12-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ff5ba39b58d84994453f28030896d4a49c7b15535e1ba88211197822a8fc048d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1180516864

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "250M"
zstd_bytes = 261546674

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220429"
previous_tag = "2022-04-29"
previous_file = "manjaro-zsh_arm64_2022-04-29_12-16-rootfs.tar.zst"
previous_sha256 = "5526d9a1d243148469427ec005159527278a7b0da9f5827e9c98a475c5f3135f"

current_version = "latest02"
current_date = "20220506"
old_file = "manjaro-zsh_arm64_2022-04-22_12-16-rootfs.tar.zst"
old_sha256 = "0cb3c9105e23a62410311dcfb88cdafd44104f622021904fb83d38865b979ec2"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2022-05-06_12-17-rootfs.tar.zst
# SHA256SUM=ff5ba39b58d84994453f28030896d4a49c7b15535e1ba88211197822a8fc048d
# BUILD_DATE=20220506
# BUILD_TAG=2022-05-06
# STATUS=completed
# VERSION=latest02
# END_TIME=12:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-06
begin = 2022-05-06 12:02:33.713699998+00:00
start-sync_0 = 12:10:00
start-zstd = 12:11:36
start-sync_1 = 12:16:40
end-sync_1 = 12:17:06
end = 2022-05-06 12:17:06.139790555+00:00

[server]
repo = "cake233/manjaro-zsh-arm64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'
```
