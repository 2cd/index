# arch-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-arm64 \
    cake233/arch-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it arch-zsh-arm64 zsh
```

## arch-zsh-arm64.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2023-05-31"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_arm64_2023-05-31_00-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "516e7700536a6f57f338a55f5e81b58da4f8dd28b3569eecddccfc3a9be132b6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1023M"
tar_bytes = 1072020992

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "239M"
zstd_bytes = 250512647

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230524"
previous_tag = "2023-05-24"
previous_file = "arch-zsh_arm64_2023-05-24_00-29-rootfs.tar.zst"
previous_sha256 = "ec944eb02dc62819eeec544455ecfb201a50c2481bc2311b48680a2cc632e81c"

current_version = "latest02"
current_date = "20230531"
old_file = "arch-zsh_arm64_2023-05-17_00-33-rootfs.tar.zst"
old_sha256 = "9c9ff5c989f687078fd19b909367180128da81edeef189579ccc28155251a58c"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2023-05-31_00-29-rootfs.tar.zst
# SHA256SUM=516e7700536a6f57f338a55f5e81b58da4f8dd28b3569eecddccfc3a9be132b6
# BUILD_DATE=20230531
# BUILD_TAG=2023-05-31
# STATUS=completed
# VERSION=latest02
# END_TIME=00:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-31
begin = 2023-05-31 00:07:38.914959093+00:00
start-sync_0 = 00:23:28
start-zstd = 00:25:00
start-sync_1 = 00:28:51
end-sync_1 = 00:29:12
end = 2023-05-31 00:29:12.047071850+00:00

[server]
repo = "cake233/arch-zsh-arm64"

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
