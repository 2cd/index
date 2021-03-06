# manjaro-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name manjaro-zsh-amd64 \
    cake233/manjaro-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it manjaro-zsh-amd64 zsh
```

## manjaro-zsh-amd64.toml

```toml
[main]
name = "manjaro"
tag = ["zsh", "2022-07-22"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_amd64_2022-07-22_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0a3b4c55bd79acbb9d1344e18c1b4aea1c164ae6650fbff35d71e085a0e5d829"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1179374592

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "269M"
zstd_bytes = 281014588

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220715"
previous_tag = "2022-07-15"
previous_file = "manjaro-zsh_amd64_2022-07-15_12-11-rootfs.tar.zst"
previous_sha256 = "e91b3bbe7042bcb348f4ee2931fd15f42922ea5a9215a4a0774de023cba58da8"

current_version = "latest01"
current_date = "20220722"
old_file = "manjaro-zsh_amd64_2022-07-08_12-11-rootfs.tar.zst"
old_sha256 = "36c6acf15d0f722fb8af5cfab8582331830d4eb65071401d5ef2759c47d541c0"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2022-07-22_12-12-rootfs.tar.zst
# SHA256SUM=0a3b4c55bd79acbb9d1344e18c1b4aea1c164ae6650fbff35d71e085a0e5d829
# BUILD_DATE=20220722
# BUILD_TAG=2022-07-22
# STATUS=completed
# VERSION=latest01
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-22
begin = 2022-07-22 12:02:26.632532332+00:00
start-sync_0 = 12:04:54
start-zstd = 12:06:28
start-sync_1 = 12:12:07
end-sync_1 = 12:12:31
end = 2022-07-22 12:12:31.557386320+00:00

[server]
repo = "cake233/manjaro-zsh-amd64"

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
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
