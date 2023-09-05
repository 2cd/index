# fedora-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name fedora-zsh-arm64 \
    cake233/fedora-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it fedora-zsh-arm64 zsh
```

## fedora-zsh-arm64.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2023-09-05"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_arm64_2023-09-05_12-35.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8aeea59a99af0a3b125f6a63c1304ef96947c13454784c8d8a2f05fd4fad1644"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1562935296

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "222M"
zstd_bytes = 231967047

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230829"
previous_tag = "2023-08-29"
previous_file = "fedora-zsh_arm64_2023-08-29_12-45-rootfs.tar.zst"
previous_sha256 = "96ca15943c9b4dce12f0506b281395529760eb04c783b86640a877e90ac31191"

current_version = "latest02"
current_date = "20230905"
old_file = "fedora-zsh_arm64_2023-08-08_12-44-rootfs.tar.zst"
old_sha256 = "a5340d8a63c54bcb8128009c8dcb9c2beb24cc81a6fb5bc024ec2dd028e0d69b"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2023-09-05_12-35-rootfs.tar.zst
# SHA256SUM=8aeea59a99af0a3b125f6a63c1304ef96947c13454784c8d8a2f05fd4fad1644
# BUILD_DATE=20230905
# BUILD_TAG=2023-09-05
# STATUS=completed
# VERSION=latest02
# END_TIME=12:35

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-05
begin = 2023-09-05 12:02:44.847724823+00:00
start-sync_0 = 12:29:33
start-zstd = 12:31:37
start-sync_1 = 12:35:40
end-sync_1 = 12:35:59
end = 2023-09-05 12:35:59.709337940+00:00

[server]
repo = "cake233/fedora-zsh-arm64"

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
ldd = 'ldd (GNU libc) 2.38.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'
```