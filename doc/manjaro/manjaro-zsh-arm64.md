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
tag = ["zsh", "2023-01-20"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_arm64_2023-01-20_12-22.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5ddb51152d58c697a4c132de83d29f8870c11b0400b4b88ba8e26c891d3247af"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1155770880

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "251M"
zstd_bytes = 262570452

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230113"
previous_tag = "2023-01-13"
previous_file = "manjaro-zsh_arm64_2023-01-13_12-25-rootfs.tar.zst"
previous_sha256 = "b5c7beb60877286d079de50685cf108bb8144bcc19da412835b199de59e787ce"

current_version = "latest02"
current_date = "20230120"
old_file = "manjaro-zsh_arm64_2023-01-06_12-20-rootfs.tar.zst"
old_sha256 = "a0bd8afa266fba2718aa3bbb85438a0a4a33fcc78151ac5ac793b5f2be8e498e"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2023-01-20_12-22-rootfs.tar.zst
# SHA256SUM=5ddb51152d58c697a4c132de83d29f8870c11b0400b4b88ba8e26c891d3247af
# BUILD_DATE=20230120
# BUILD_TAG=2023-01-20
# STATUS=completed
# VERSION=latest02
# END_TIME=12:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-20
begin = 2023-01-20 12:02:28.617265033+00:00
start-sync_0 = 12:15:44
start-zstd = 12:17:33
start-sync_1 = 12:22:16
end-sync_1 = 12:22:41
end = 2023-01-20 12:22:41.892673091+00:00

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
