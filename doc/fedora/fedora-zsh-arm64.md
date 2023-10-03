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
tag = ["zsh", "2023-10-03"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_arm64_2023-10-03_12-51.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4191e4537c89a5e08df6cd059d32c7eddf33d928121a7e35b7d6caeb72584e7c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1558156288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "221M"
zstd_bytes = 231642562

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230926"
previous_tag = "2023-09-26"
previous_file = "fedora-zsh_arm64_2023-09-26_12-52-rootfs.tar.zst"
previous_sha256 = "bbd8183a10ac1ce1016bd8d75f650e921ad1d843f52f9b8431d9bddc4a46eeac"

current_version = "latest02"
current_date = "20231003"
old_file = "fedora-zsh_arm64_2023-09-19_12-55-rootfs.tar.zst"
old_sha256 = "6e098d97636402648afd8adcb2259577e347208757c99a54b48049864549ee41"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2023-10-03_12-51-rootfs.tar.zst
# SHA256SUM=4191e4537c89a5e08df6cd059d32c7eddf33d928121a7e35b7d6caeb72584e7c
# BUILD_DATE=20231003
# BUILD_TAG=2023-10-03
# STATUS=completed
# VERSION=latest02
# END_TIME=12:51

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-03
begin = 2023-10-03 12:02:36.849928530+00:00
start-sync_0 = 12:44:37
start-zstd = 12:46:44
start-sync_1 = 12:50:46
end-sync_1 = 12:51:14
end = 2023-10-03 12:51:14.089339870+00:00

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
