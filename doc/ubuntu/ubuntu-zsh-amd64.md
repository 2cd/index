# ubuntu-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-zsh-amd64 \
    cake233/ubuntu-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it ubuntu-zsh-amd64 zsh
```

## ubuntu-zsh-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2022-06-14", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_amd64_2022-06-14_00-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "937de41be483a1d428fb60d63baac62f2cbe1a4f247547e9f544615bcd59c3f7"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "638M"
tar_bytes = 668489216

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "115M"
zstd_bytes = 120116420

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220607"
previous_tag = "2022-06-07"
previous_file = "ubuntu-zsh_amd64_2022-06-07_00-08-rootfs.tar.zst"
previous_sha256 = "8ade3cf53ba213e2332f16b7deb1a3c914a9fc4dabfb4198751dc1257a988153"

current_version = "latest02"
current_date = "20220614"
old_file = "ubuntu-zsh_amd64_2022-05-31_00-08-rootfs.tar.zst"
old_sha256 = "519071bcfd9110be832d4b4b1850af09c3ae7435a9103cf7a2cc3ad3601a0b48"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-zsh_amd64_2022-06-14_00-08-rootfs.tar.zst
# SHA256SUM=937de41be483a1d428fb60d63baac62f2cbe1a4f247547e9f544615bcd59c3f7
# BUILD_DATE=20220614
# BUILD_TAG=2022-06-14
# STATUS=completed
# VERSION=latest02
# END_TIME=00:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-14
begin = 2022-06-14 00:02:26.145807771+00:00
start-sync_0 = 00:04:14
start-zstd = 00:05:56
start-sync_1 = 00:08:15
end-sync_1 = 00:08:29
end = 2022-06-14 00:08:29.437523794+00:00

[server]
repo = "cake233/ubuntu-zsh-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'
```
