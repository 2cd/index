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
tag = ["zsh", "2022-09-02"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_amd64_2022-09-02_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "cd27c1f00e5a0af8f65019770eb90b5360b823cd7d4d562098d3d62a05b3abda"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1116713984

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "262M"
zstd_bytes = 274015648

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220826"
previous_tag = "2022-08-26"
previous_file = "manjaro-zsh_amd64_2022-08-26_12-14-rootfs.tar.zst"
previous_sha256 = "c00c704f35285ba63ef375acf7a90387b818cc1f014c6156acb6d3a12b285dbb"

current_version = "latest01"
current_date = "20220902"
old_file = "manjaro-zsh_amd64_2022-08-19_12-11-rootfs.tar.zst"
old_sha256 = "72e75200ee78354c4b65f339135b1db81543493db566d9c0c6f83255523bf478"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2022-09-02_12-11-rootfs.tar.zst
# SHA256SUM=cd27c1f00e5a0af8f65019770eb90b5360b823cd7d4d562098d3d62a05b3abda
# BUILD_DATE=20220902
# BUILD_TAG=2022-09-02
# STATUS=completed
# VERSION=latest01
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-02
begin = 2022-09-02 12:02:21.216114211+00:00
start-sync_0 = 12:05:34
start-zstd = 12:07:15
start-sync_1 = 12:11:11
end-sync_1 = 12:11:32
end = 2022-09-02 12:11:32.821324273+00:00

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
