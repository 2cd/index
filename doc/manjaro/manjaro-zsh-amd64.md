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
tag = ["zsh", "2023-01-13"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_amd64_2023-01-13_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7b2e39e83ccaa458bce8c520d4a173374ac8cdb1b48119d20806cfa15bd4f840"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1184315904

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "276M"
zstd_bytes = 288846373

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230106"
previous_tag = "2023-01-06"
previous_file = "manjaro-zsh_amd64_2023-01-06_12-11-rootfs.tar.zst"
previous_sha256 = "334f433bb96b5b76b01a868d5c6e97e7d9d657a4847b9d3fc089f030ebe0fa43"

current_version = "latest01"
current_date = "20230113"
old_file = "manjaro-zsh_amd64_2022-12-30_12-11-rootfs.tar.zst"
old_sha256 = "408a510337ab819800c67ad4720e9715fa1def474545b507925a6af578e097f8"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2023-01-13_12-10-rootfs.tar.zst
# SHA256SUM=7b2e39e83ccaa458bce8c520d4a173374ac8cdb1b48119d20806cfa15bd4f840
# BUILD_DATE=20230113
# BUILD_TAG=2023-01-13
# STATUS=completed
# VERSION=latest01
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-13
begin = 2023-01-13 12:02:24.974851945+00:00
start-sync_0 = 12:04:42
start-zstd = 12:06:23
start-sync_1 = 12:10:27
end-sync_1 = 12:10:47
end = 2023-01-13 12:10:47.022993574+00:00

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
