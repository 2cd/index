# ubuntu-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-zsh-armv7 \
    cake233/ubuntu-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it ubuntu-zsh-armv7 zsh
```

## ubuntu-zsh-armv7.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2022-03-01", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "ubuntu-zsh_armhf_2022-03-01_00-23.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "50c76dd81dc2a52f89fe6fd8e88b7b11860d31cc640c68b729397895c7cba031"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "574M"
tar_bytes = 601625600

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "108M"
zstd_bytes = 112820163

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220222"
previous_tag = "2022-02-22"
previous_file = "ubuntu-zsh_armhf_2022-02-22_00-20-rootfs.tar.zst"
previous_sha256 = "1c4c94985bb0666da17c974812eb96832a78ce8b3d88bc5ac5adcb8890f73cea"

current_version = "latest02"
current_date = "20220301"
old_file = "ubuntu-zsh_armhf_2022-02-15_00-21-rootfs.tar.zst"
old_sha256 = "ca56f355e97f5764656b6a053b73f215792433c5d4e91281ce755bd9914d6b8e"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-zsh_armhf_2022-03-01_00-23-rootfs.tar.zst
# SHA256SUM=50c76dd81dc2a52f89fe6fd8e88b7b11860d31cc640c68b729397895c7cba031
# BUILD_DATE=20220301
# BUILD_TAG=2022-03-01
# STATUS=completed
# VERSION=latest02
# END_TIME=00:23

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-01
begin = 2022-03-01 00:02:28.233717830+00:00
start-sync_0 = 00:19:20
start-zstd = 00:21:15
start-sync_1 = 00:23:35
end-sync_1 = 00:23:54
end = 2022-03-01 00:23:54.731397397+00:00

[server]
repo = "cake233/ubuntu-zsh-armv7"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu1) 2.35'
zsh = 'zsh 5.8.1 (arm-unknown-linux-gnueabihf)'
```
