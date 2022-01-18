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
tag = ["zsh", "2022-01-18", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "ubuntu-zsh_armhf_2022-01-18_00-16.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "294c2805b89a588cd1504de98b2bce6cb68bb08eba8509aa5aff23cb2cabd276"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "573M"
tar_bytes = 599845888

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "107M"
zstd_bytes = 111981732

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220111"
previous_tag = "2022-01-11"
previous_file = "ubuntu-zsh_armhf_2022-01-11_00-19-rootfs.tar.zst"
previous_sha256 = "c7ba204f77eb4fc13d0af4a4d84fc0de833ef0b853a7894488b261506ef02a7c"

current_version = "latest01"
current_date = "20220118"
old_file = "ubuntu-zsh_armhf_2022-01-04_00-22-rootfs.tar.zst"
old_sha256 = "5982d1c39674088025c494ee9e398da689c206747b910b755f383daa70d7a521"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-zsh_armhf_2022-01-18_00-16-rootfs.tar.zst
# SHA256SUM=294c2805b89a588cd1504de98b2bce6cb68bb08eba8509aa5aff23cb2cabd276
# BUILD_DATE=20220118
# BUILD_TAG=2022-01-18
# STATUS=completed
# VERSION=latest01
# END_TIME=00:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-18
begin = 2022-01-18 00:02:22.080962450+00:00
start-sync_0 = 00:13:08
start-zstd = 00:14:48
start-sync_1 = 00:16:36
end-sync_1 = 00:16:48
end = 2022-01-18 00:16:48.428721348+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.34-0ubuntu3) 2.34'
zsh = 'zsh 5.8 (arm-unknown-linux-gnueabihf)'
```
