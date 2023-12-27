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
tag = ["zsh", "2023-12-27"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_arm64_2023-12-27_12-30.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0e4abf3a5e4d20c60535b719f46d44e623f0d30c72923090ad271ec0b46a33b3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "824M"
tar_bytes = 863837184

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "151M"
zstd_bytes = 157396903

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-zsh_arm64_2023-11-22_12-31-rootfs.tar.zst"
previous_sha256 = "e42cd7823cc46adf76190a5e056d10b7ccfbdf87f330127e25bb0f770ecb6abf"

current_version = "latest01"
current_date = "20231227"
old_file = "debian-zsh_arm64_2023-11-15_12-31-rootfs.tar.zst"
old_sha256 = "2edbc6d9efef4ab87d393f962ca8986d24998e018bdec122b6a538cbcfff868c"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2023-12-27_12-30-rootfs.tar.zst
# SHA256SUM=0e4abf3a5e4d20c60535b719f46d44e623f0d30c72923090ad271ec0b46a33b3
# BUILD_DATE=20231227
# BUILD_TAG=2023-12-27
# STATUS=completed
# VERSION=latest01
# END_TIME=12:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-27
begin = 2023-12-27 12:02:30.757488096+00:00
start-sync_0 = 12:26:44
start-zstd = 12:28:24
start-sync_1 = 12:30:38
end-sync_1 = 12:30:50
end = 2023-12-27 12:30:50.492567286+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-13) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
