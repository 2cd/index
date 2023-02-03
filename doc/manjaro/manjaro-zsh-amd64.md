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
tag = ["zsh", "2023-02-03"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_amd64_2023-02-03_12-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "82e6dced5ff9340e00482e32a50a041294bb48e5cba2616e83c34c57b58b396c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1187725824

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "277M"
zstd_bytes = 289919192

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230127"
previous_tag = "2023-01-27"
previous_file = "manjaro-zsh_amd64_2023-01-27_12-11-rootfs.tar.zst"
previous_sha256 = "5323fc438bafe980c197ab6d4e384993acd0d7c20bf5590145fd12e6e3f1950d"

current_version = "latest02"
current_date = "20230203"
old_file = "manjaro-zsh_amd64_2023-01-20_12-11-rootfs.tar.zst"
old_sha256 = "8bf06142dbc3c00c88536860a1d61abda578c6fc89683cd524f41daf866a02ba"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2023-02-03_12-13-rootfs.tar.zst
# SHA256SUM=82e6dced5ff9340e00482e32a50a041294bb48e5cba2616e83c34c57b58b396c
# BUILD_DATE=20230203
# BUILD_TAG=2023-02-03
# STATUS=completed
# VERSION=latest02
# END_TIME=12:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-03
begin = 2023-02-03 12:02:28.214094096+00:00
start-sync_0 = 12:05:27
start-zstd = 12:07:20
start-sync_1 = 12:12:34
end-sync_1 = 12:13:00
end = 2023-02-03 12:13:00.182194236+00:00

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
ldd = 'ldd (GNU libc) 2.36'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
