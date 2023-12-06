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
tag = ["zsh", "2023-12-06"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_arm64_2023-12-06_12-32.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ee2b06db467e20745ccfcf632d3a01e0d29bd593e824781ec53cf4f92142bfc5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "824M"
tar_bytes = 863020544

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "151M"
zstd_bytes = 157589624

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-zsh_arm64_2023-11-22_12-31-rootfs.tar.zst"
previous_sha256 = "e42cd7823cc46adf76190a5e056d10b7ccfbdf87f330127e25bb0f770ecb6abf"

current_version = "latest01"
current_date = "20231206"
old_file = "debian-zsh_arm64_2023-11-15_12-31-rootfs.tar.zst"
old_sha256 = "2edbc6d9efef4ab87d393f962ca8986d24998e018bdec122b6a538cbcfff868c"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2023-12-06_12-32-rootfs.tar.zst
# SHA256SUM=ee2b06db467e20745ccfcf632d3a01e0d29bd593e824781ec53cf4f92142bfc5
# BUILD_DATE=20231206
# BUILD_TAG=2023-12-06
# STATUS=completed
# VERSION=latest01
# END_TIME=12:32

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-06
begin = 2023-12-06 12:02:36.670351370+00:00
start-sync_0 = 12:28:38
start-zstd = 12:30:22
start-sync_1 = 12:32:38
end-sync_1 = 12:32:53
end = 2023-12-06 12:32:53.824583401+00:00

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
