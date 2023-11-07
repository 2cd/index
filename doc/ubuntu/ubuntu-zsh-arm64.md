# ubuntu-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-zsh-arm64 \
    cake233/ubuntu-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it ubuntu-zsh-arm64 zsh
```

## ubuntu-zsh-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2023-11-07", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_arm64_2023-11-07_00-23.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ab331f343863a3bad33b555012b1f0f8bc4f09413b1b7a4a3ee5bea0bbd11a5c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "803M"
tar_bytes = 841475584

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "151M"
zstd_bytes = 158241699

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231024"
previous_tag = "2023-10-24"
previous_file = "ubuntu-zsh_arm64_2023-10-24_00-28-rootfs.tar.zst"
previous_sha256 = "fc5df784fb5814d9eeada6697b1e41be7e576cfd8cb33d20e7626f81b5d03613"

current_version = "latest02"
current_date = "20231107"
old_file = "ubuntu-zsh_arm64_2023-10-17_00-33-rootfs.tar.zst"
old_sha256 = "430b7bc8254bef23f902bfb04326c1f4a943a685d54761980b45aede69153ef3"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-zsh_arm64_2023-11-07_00-23-rootfs.tar.zst
# SHA256SUM=ab331f343863a3bad33b555012b1f0f8bc4f09413b1b7a4a3ee5bea0bbd11a5c
# BUILD_DATE=20231107
# BUILD_TAG=2023-11-07
# STATUS=completed
# VERSION=latest02
# END_TIME=00:23

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-07
begin = 2023-11-07 00:02:30.381912575+00:00
start-sync_0 = 00:19:58
start-zstd = 00:21:37
start-sync_1 = 00:23:40
end-sync_1 = 00:23:57
end = 2023-11-07 00:23:57.030480884+00:00

[server]
repo = "cake233/ubuntu-zsh-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu6) 2.38'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
