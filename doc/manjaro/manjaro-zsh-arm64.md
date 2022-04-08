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
tag = ["zsh", "2022-04-08"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "manjaro-zsh_arm64_2022-04-08_11-17.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "5ee26ede042f54acd146ddeb968601f4712b56e55f5f2ae62924d99c6f2a530a"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1177583104

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "249M"
zstd_bytes = 260788954

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220401"
previous_tag = "2022-04-01"
previous_file = "manjaro-zsh_arm64_2022-04-01_11-18-rootfs.tar.zst"
previous_sha256 = "caa17ebd40ab5b2f6914e6ffdd254ec673af96fd90a67deccb086fb51078fb87"

current_version = "latest02"
current_date = "20220408"
old_file = "manjaro-zsh_arm64_2022-03-25_12-16-rootfs.tar.zst"
old_sha256 = "8d99502bea5b9e7db0f9c2ef18b077657510ba64b9047114367d9d3336c5dafc"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2022-04-08_11-17-rootfs.tar.zst
# SHA256SUM=5ee26ede042f54acd146ddeb968601f4712b56e55f5f2ae62924d99c6f2a530a
# BUILD_DATE=20220408
# BUILD_TAG=2022-04-08
# STATUS=completed
# VERSION=latest02
# END_TIME=11:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-08
begin = 2022-04-08 11:02:27.666154142+00:00
start-sync_0 = 11:10:17
start-zstd = 11:11:48
start-sync_1 = 11:16:42
end-sync_1 = 11:17:03
end = 2022-04-08 11:17:03.163088186+00:00

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'
```
