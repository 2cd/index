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
tag = ["zsh", "2022-07-19", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_armhf_2022-07-19_00-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a401f32de83a1119bb7a5b04c156a5aaf3da4a1f2375d4275d13c5a41adfe964"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "635M"
tar_bytes = 664993792

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "127M"
zstd_bytes = 132459364

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220712"
previous_tag = "2022-07-12"
previous_file = "ubuntu-zsh_armhf_2022-07-12_00-19-rootfs.tar.zst"
previous_sha256 = "2f028933498788e280a0dd34db8f417f064e78358b8ef5535bf79be6cf56a5d8"

current_version = "latest01"
current_date = "20220719"
old_file = "ubuntu-zsh_armhf_2022-07-05_00-18-rootfs.tar.zst"
old_sha256 = "ab18202ab5b60635c78990a3e48c75999411f2dfd77a65f17bfadcd213e423d9"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-zsh_armhf_2022-07-19_00-18-rootfs.tar.zst
# SHA256SUM=a401f32de83a1119bb7a5b04c156a5aaf3da4a1f2375d4275d13c5a41adfe964
# BUILD_DATE=20220719
# BUILD_TAG=2022-07-19
# STATUS=completed
# VERSION=latest01
# END_TIME=00:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-19
begin = 2022-07-19 00:02:35.929127068+00:00
start-sync_0 = 00:14:04
start-zstd = 00:15:51
start-sync_1 = 00:18:03
end-sync_1 = 00:18:19
end = 2022-07-19 00:18:19.707342275+00:00

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
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```
