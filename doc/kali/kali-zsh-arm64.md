# kali-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-arm64 \
    cake233/kali-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it kali-zsh-arm64 zsh
```

## kali-zsh-arm64.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2022-08-04"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_arm64_2022-08-04_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "dbade9e6a69c3fc53eaa8727c1d9bf73cad34a9966db34bbc000a71a110ac1de"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "777M"
tar_bytes = 813877248

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "147M"
zstd_bytes = 153735729

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220714"
previous_tag = "2022-07-14"
previous_file = "kali-zsh_arm64_2022-07-14_12-18-rootfs.tar.zst"
previous_sha256 = "3e8e732ca3a12c3538206dcb50831d335650d79a64905d8ab5278e8228ac8126"

current_version = "latest01"
current_date = "20220804"
old_file = "kali-zsh_arm64_2022-07-07_12-25-rootfs.tar.zst"
old_sha256 = "4bae5984d76a0308fc73047d3334bf76a32b673dbc9070a9223d6e9bb502ed50"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-zsh_arm64_2022-08-04_12-18-rootfs.tar.zst
# SHA256SUM=dbade9e6a69c3fc53eaa8727c1d9bf73cad34a9966db34bbc000a71a110ac1de
# BUILD_DATE=20220804
# BUILD_TAG=2022-08-04
# STATUS=completed
# VERSION=latest01
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-04
begin = 2022-08-04 12:02:26.862504300+00:00
start-sync_0 = 12:14:26
start-zstd = 12:16:17
start-sync_1 = 12:18:34
end-sync_1 = 12:18:50
end = 2022-08-04 12:18:50.725223249+00:00

[server]
repo = "cake233/kali-zsh-arm64"

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
ldd = 'ldd (Debian GLIBC 2.33-8) 2.33'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
