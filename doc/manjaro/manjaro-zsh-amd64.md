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
tag = ["zsh", "2023-06-09"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_amd64_2023-06-09_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "979b7c01ffd9d42c40d5e0dce7afaad2596790eece8a683b906b34e608d98a64"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1248237056

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "287M"
zstd_bytes = 300071721

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230602"
previous_tag = "2023-06-02"
previous_file = "manjaro-zsh_amd64_2023-06-02_12-12-rootfs.tar.zst"
previous_sha256 = "ab34ba1b2fc129341818d566df2f0087cb5d9f7bc03ff13b9987b266245e1140"

current_version = "latest01"
current_date = "20230609"
old_file = "manjaro-zsh_amd64_2023-05-26_12-13-rootfs.tar.zst"
old_sha256 = "6c72e43d45a51f4b087427a032fd25f21ad76eb234622d5e15e26f0bc7eb10dc"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2023-06-09_12-12-rootfs.tar.zst
# SHA256SUM=979b7c01ffd9d42c40d5e0dce7afaad2596790eece8a683b906b34e608d98a64
# BUILD_DATE=20230609
# BUILD_TAG=2023-06-09
# STATUS=completed
# VERSION=latest01
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-09
begin = 2023-06-09 12:02:37.042409393+00:00
start-sync_0 = 12:05:23
start-zstd = 12:07:14
start-sync_1 = 12:12:09
end-sync_1 = 12:12:36
end = 2023-06-09 12:12:36.407964919+00:00

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
