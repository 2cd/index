# arch-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-arm64 \
    cake233/arch-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it arch-zsh-arm64 zsh
```

## arch-zsh-arm64.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2022-03-16"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "arch-zsh_arm64_2022-03-16_00-25.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "1115591ce56ee89f43b998f8b1365d88625f1be6a723253369fd3c29c88762ce"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "955M"
tar_bytes = 1000822784

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "224M"
zstd_bytes = 233981084

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220309"
previous_tag = "2022-03-09"
previous_file = "arch-zsh_arm64_2022-03-09_00-28-rootfs.tar.zst"
previous_sha256 = "cbd93cef6473528ba094793c76890ea61019216e97760eadb9b51088bbfe6b49"

current_version = "latest01"
current_date = "20220316"
old_file = "arch-zsh_arm64_2022-03-02_00-30-rootfs.tar.zst"
old_sha256 = "344eeb460a13e1d08b02e7e5d2ca5cfe83522c818ce4ed0d6b293da567399312"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2022-03-16_00-25-rootfs.tar.zst
# SHA256SUM=1115591ce56ee89f43b998f8b1365d88625f1be6a723253369fd3c29c88762ce
# BUILD_DATE=20220316
# BUILD_TAG=2022-03-16
# STATUS=completed
# VERSION=latest01
# END_TIME=00:25

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-16
begin = 2022-03-16 00:06:52.569784942+00:00
start-sync_0 = 00:19:53
start-zstd = 00:21:32
start-sync_1 = 00:25:03
end-sync_1 = 00:25:29
end = 2022-03-16 00:25:29.392199949+00:00

[server]
repo = "cake233/arch-zsh-arm64"

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
