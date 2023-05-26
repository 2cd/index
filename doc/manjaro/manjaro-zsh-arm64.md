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
tag = ["zsh", "2023-05-26"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_arm64_2023-05-26_12-22.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e22e1c52b3754a67e5cd9d4c4ae79ba9d15f35a72289afec14b39587f6b74161"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1166280704

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "254M"
zstd_bytes = 265445378

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230519"
previous_tag = "2023-05-19"
previous_file = "manjaro-zsh_arm64_2023-05-19_12-20-rootfs.tar.zst"
previous_sha256 = "5eefc0cd2b56b14217708ccf2824b4c4052fc25727a1bb43a2c740a18f7a91ba"

current_version = "latest02"
current_date = "20230526"
old_file = "manjaro-zsh_arm64_2023-05-12_12-22-rootfs.tar.zst"
old_sha256 = "d818ca6571e8d64c07faf37413610730fabab4adda6f3711b1cf4581a7423eff"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2023-05-26_12-22-rootfs.tar.zst
# SHA256SUM=e22e1c52b3754a67e5cd9d4c4ae79ba9d15f35a72289afec14b39587f6b74161
# BUILD_DATE=20230526
# BUILD_TAG=2023-05-26
# STATUS=completed
# VERSION=latest02
# END_TIME=12:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-26
begin = 2023-05-26 12:02:36.450186913+00:00
start-sync_0 = 12:15:48
start-zstd = 12:17:32
start-sync_1 = 12:22:37
end-sync_1 = 12:22:58
end = 2023-05-26 12:22:58.974347005+00:00

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
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
