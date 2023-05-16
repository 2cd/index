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
tag = ["zsh", "2023-05-16"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_arm64_2023-05-16_13-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b35ba21e5337980b2998bb5e6f9ff1f1d47f4b9fd5a5c12f25e0801f0baf5a3c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1550544384

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "220M"
zstd_bytes = 229885857

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230502"
previous_tag = "2023-05-02"
previous_file = "fedora-zsh_arm64_2023-05-02_13-00-rootfs.tar.zst"
previous_sha256 = "7d90f36c48bdafb0ffd9979a087c2fa4331dd250877f3adb80d02e8fa03014a9"

current_version = "latest02"
current_date = "20230516"
old_file = "fedora-zsh_arm64_2023-04-25_12-51-rootfs.tar.zst"
old_sha256 = "6f911ff02ee0c5d9a2df6e5f99301ff35c2092362318fcf2f2214c42e263ebac"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2023-05-16_13-03-rootfs.tar.zst
# SHA256SUM=b35ba21e5337980b2998bb5e6f9ff1f1d47f4b9fd5a5c12f25e0801f0baf5a3c
# BUILD_DATE=20230516
# BUILD_TAG=2023-05-16
# STATUS=completed
# VERSION=latest02
# END_TIME=13:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-16
begin = 2023-05-16 12:02:37.591585799+00:00
start-sync_0 = 12:55:41
start-zstd = 12:58:04
start-sync_1 = 13:02:39
end-sync_1 = 13:03:03
end = 2023-05-16 13:03:03.039831208+00:00

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
ldd = 'ldd (GNU libc) 2.37.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'
```
