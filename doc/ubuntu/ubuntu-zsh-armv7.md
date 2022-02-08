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
tag = ["zsh", "2022-02-08", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "ubuntu-zsh_armhf_2022-02-08_00-20.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "c5e5f188bd67f278fa2a64a92730bdea5d5e6d2698b056d0adf75ac2c11bd72a"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "574M"
tar_bytes = 600989696

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "108M"
zstd_bytes = 112444437

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220201"
previous_tag = "2022-02-01"
previous_file = "ubuntu-zsh_armhf_2022-02-01_00-20-rootfs.tar.zst"
previous_sha256 = "0fd5200194189921758c80a8ad66f71fb398ecc6e32763448d20edb34aa77ee8"

current_version = "latest01"
current_date = "20220208"
old_file = "ubuntu-zsh_armhf_2022-01-25_00-20-rootfs.tar.zst"
old_sha256 = "79e71b268d346daa5ac6dfd866bfad6c275d96827e5e2a98dd3a87885648119e"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-zsh_armhf_2022-02-08_00-20-rootfs.tar.zst
# SHA256SUM=c5e5f188bd67f278fa2a64a92730bdea5d5e6d2698b056d0adf75ac2c11bd72a
# BUILD_DATE=20220208
# BUILD_TAG=2022-02-08
# STATUS=completed
# VERSION=latest01
# END_TIME=00:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-08
begin = 2022-02-08 00:02:26.658044781+00:00
start-sync_0 = 00:16:05
start-zstd = 00:17:48
start-sync_1 = 00:19:56
end-sync_1 = 00:20:09
end = 2022-02-08 00:20:09.488159855+00:00

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
