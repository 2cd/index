# debian-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-arm64 \
    cake233/debian-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it debian-zsh-arm64 zsh
```

## debian-zsh-arm64.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2022-07-20"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_arm64_2022-07-20_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a8726ebd356788c5a5eee80ac4fe51ba2dfe4219c8fcfa30bad24083bd5df708"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "776M"
tar_bytes = 813597184

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "147M"
zstd_bytes = 153666427

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220713"
previous_tag = "2022-07-13"
previous_file = "debian-zsh_arm64_2022-07-13_12-21-rootfs.tar.zst"
previous_sha256 = "7d0a97d83937fe63f26b5b9f47a3f02e79160702dd0aeed2b7cf7892c93ba8ef"

current_version = "latest01"
current_date = "20220720"
old_file = "debian-zsh_arm64_2022-07-06_12-17-rootfs.tar.zst"
old_sha256 = "b45b98e96a4f314719ae54618a7cbf8d6903d87cdc5015531ae672f3bcf422e8"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2022-07-20_12-18-rootfs.tar.zst
# SHA256SUM=a8726ebd356788c5a5eee80ac4fe51ba2dfe4219c8fcfa30bad24083bd5df708
# BUILD_DATE=20220720
# BUILD_TAG=2022-07-20
# STATUS=completed
# VERSION=latest01
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-20
begin = 2022-07-20 12:02:27.620853980+00:00
start-sync_0 = 12:13:32
start-zstd = 12:15:19
start-sync_1 = 12:18:14
end-sync_1 = 12:18:28
end = 2022-07-20 12:18:28.855525438+00:00

[server]
repo = "cake233/debian-zsh-arm64"

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
