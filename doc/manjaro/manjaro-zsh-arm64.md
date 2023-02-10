# manjaro-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name manjaro-zsh-arm64 \
    cake233/manjaro-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it manjaro-zsh-arm64 zsh
```

## manjaro-zsh-arm64.toml

```toml
[main]
name = "manjaro"
tag = ["zsh", "2023-02-10"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_arm64_2023-02-10_12-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8e5ec2fba1b50b7a7a97bce1149e1832989f81e319b61ea9491bbdc78e0aba4d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1158916608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "253M"
zstd_bytes = 264554002

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230203"
previous_tag = "2023-02-03"
previous_file = "manjaro-zsh_arm64_2023-02-03_12-19-rootfs.tar.zst"
previous_sha256 = "629d257aef7d4e44f0b43204d63558c8f74003b29ac4f2009de574252d02c60b"

current_version = "latest01"
current_date = "20230210"
old_file = "manjaro-zsh_arm64_2023-01-27_12-19-rootfs.tar.zst"
old_sha256 = "8fd922fd7fe59d399eb5d9af324502d86b33d9c028ec32628733f504449ca541"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2023-02-10_12-20-rootfs.tar.zst
# SHA256SUM=8e5ec2fba1b50b7a7a97bce1149e1832989f81e319b61ea9491bbdc78e0aba4d
# BUILD_DATE=20230210
# BUILD_TAG=2023-02-10
# STATUS=completed
# VERSION=latest01
# END_TIME=12:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-10
begin = 2023-02-10 12:02:33.849790012+00:00
start-sync_0 = 12:14:00
start-zstd = 12:15:41
start-sync_1 = 12:20:20
end-sync_1 = 12:20:42
end = 2023-02-10 12:20:42.527457128+00:00

[server]
repo = "cake233/manjaro-zsh-arm64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
