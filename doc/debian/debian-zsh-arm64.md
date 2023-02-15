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
tag = ["zsh", "2023-02-15"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_arm64_2023-02-15_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1f8fd392be30fe909b42e1901578715bc1bd2215f05ce02288903b4d53d898b7"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "814M"
tar_bytes = 853066752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "149M"
zstd_bytes = 155674643

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230208"
previous_tag = "2023-02-08"
previous_file = "debian-zsh_arm64_2023-02-08_12-22-rootfs.tar.zst"
previous_sha256 = "d8e56ad9c8e4e2e4dab28a8d5ed7373d704a2d4545a44dbf38fe2b5f724b76f8"

current_version = "latest02"
current_date = "20230215"
old_file = "debian-zsh_arm64_2023-02-01_12-17-rootfs.tar.zst"
old_sha256 = "2d13f4b3ba7d9bdde4f4d77f917a51371213d85a2ec39ca7609cbe010c58d748"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2023-02-15_12-18-rootfs.tar.zst
# SHA256SUM=1f8fd392be30fe909b42e1901578715bc1bd2215f05ce02288903b4d53d898b7
# BUILD_DATE=20230215
# BUILD_TAG=2023-02-15
# STATUS=completed
# VERSION=latest02
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-15
begin = 2023-02-15 12:02:27.721319742+00:00
start-sync_0 = 12:13:25
start-zstd = 12:15:14
start-sync_1 = 12:17:51
end-sync_1 = 12:18:09
end = 2023-02-15 12:18:09.267368261+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
