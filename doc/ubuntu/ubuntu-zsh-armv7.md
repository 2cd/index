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
tag = ["zsh", "2022-04-26", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_armhf_2022-04-26_00-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "38e2ef48efd905e7df0cf3929d41fc89679636c9c211f013ad449e42235c9c5a"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "574M"
tar_bytes = 601382912

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "109M"
zstd_bytes = 113368461

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220419"
previous_tag = "2022-04-19"
previous_file = "ubuntu-zsh_armhf_2022-04-19_00-19-rootfs.tar.zst"
previous_sha256 = "cde394082c84fbee0da5cf7993512129de30fbfb789afba5d4c9e3e418e3630a"

current_version = "latest02"
current_date = "20220426"
old_file = "ubuntu-zsh_armhf_2022-04-11_23-17-rootfs.tar.zst"
old_sha256 = "54c393f99fef4e1d63dcec57d231bcbfdc11eafb83b9caf0e1eb8ca01c1f246f"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-zsh_armhf_2022-04-26_00-20-rootfs.tar.zst
# SHA256SUM=38e2ef48efd905e7df0cf3929d41fc89679636c9c211f013ad449e42235c9c5a
# BUILD_DATE=20220426
# BUILD_TAG=2022-04-26
# STATUS=completed
# VERSION=latest02
# END_TIME=00:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-26
begin = 2022-04-26 00:02:35.009664772+00:00
start-sync_0 = 00:16:11
start-zstd = 00:18:09
start-sync_1 = 00:20:25
end-sync_1 = 00:20:42
end = 2022-04-26 00:20:42.811531780+00:00

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
zsh = 'zsh 5.8.1 (arm-unknown-linux-gnueabihf)'
```
