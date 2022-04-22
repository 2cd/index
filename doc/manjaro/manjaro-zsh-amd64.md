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
tag = ["zsh", "2022-04-22"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "manjaro-zsh_amd64_2022-04-22_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2737301962323a4d6a531562ec5128d45b9da835e1ca0d450622f3e558b8ce1f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1160114688

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "260M"
zstd_bytes = 271586337

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220415"
previous_tag = "2022-04-15"
previous_file = "manjaro-zsh_amd64_2022-04-15_12-12-rootfs.tar.zst"
previous_sha256 = "7b753e2eaa541d62a6f57f49ffa5ad2b50e1310bba265a1f1cf73ab3ffc8beba"

current_version = "latest02"
current_date = "20220422"
old_file = "manjaro-zsh_amd64_2022-04-08_11-09-rootfs.tar.zst"
old_sha256 = "e73d2cccad6fe5d922bda34e7c90763d38637b34f6f0c03886543064d54b6890"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2022-04-22_12-11-rootfs.tar.zst
# SHA256SUM=2737301962323a4d6a531562ec5128d45b9da835e1ca0d450622f3e558b8ce1f
# BUILD_DATE=20220422
# BUILD_TAG=2022-04-22
# STATUS=completed
# VERSION=latest02
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-22
begin = 2022-04-22 12:02:31.023952606+00:00
start-sync_0 = 12:04:55
start-zstd = 12:06:24
start-sync_1 = 12:11:11
end-sync_1 = 12:11:33
end = 2022-04-22 12:11:33.752440018+00:00

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
zsh = 'zsh 5.8.1 (x86_64-pc-linux-gnu)'
```
