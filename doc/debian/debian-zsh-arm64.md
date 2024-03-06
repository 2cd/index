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
tag = ["zsh", "2024-03-06"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_arm64_2024-03-06_12-41.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "52a6f37b6390e3dcfeaf3ba57a678db51652e26ae2f1cbbef7f3ee3fc333ab20"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "825M"
tar_bytes = 864264704

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "153M"
zstd_bytes = 160061799

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-zsh_arm64_2023-11-22_12-31-rootfs.tar.zst"
previous_sha256 = "e42cd7823cc46adf76190a5e056d10b7ccfbdf87f330127e25bb0f770ecb6abf"

current_version = "latest01"
current_date = "20240306"
old_file = "debian-zsh_arm64_2023-11-15_12-31-rootfs.tar.zst"
old_sha256 = "2edbc6d9efef4ab87d393f962ca8986d24998e018bdec122b6a538cbcfff868c"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2024-03-06_12-41-rootfs.tar.zst
# SHA256SUM=52a6f37b6390e3dcfeaf3ba57a678db51652e26ae2f1cbbef7f3ee3fc333ab20
# BUILD_DATE=20240306
# BUILD_TAG=2024-03-06
# STATUS=completed
# VERSION=latest01
# END_TIME=12:41

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-03-06
begin = 2024-03-06 12:02:39.583779905+00:00
start-sync_0 = 12:37:13
start-zstd = 12:38:51
start-sync_1 = 12:41:07
end-sync_1 = 12:41:20
end = 2024-03-06 12:41:20.036158885+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-15.1) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
