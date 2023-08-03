# kali-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-armv7 \
    cake233/kali-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it kali-zsh-armv7 zsh
```

## kali-zsh-armv7.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2023-08-03"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_armhf_2023-08-03_12-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "260bce37ea3f2c0122c6701ae48d1cb0a50e5a366c963ae80c3c199aa59703a9"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "742M"
tar_bytes = 777586176

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "145M"
zstd_bytes = 151074211

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230727"
previous_tag = "2023-07-27"
previous_file = "kali-zsh_armhf_2023-07-27_12-32-rootfs.tar.zst"
previous_sha256 = "3dfbdcaa53f83efd39c4b1edaaeed6ad75156c8b0e835be45c3d5b0367298c18"

current_version = "latest02"
current_date = "20230803"
old_file = "kali-zsh_armhf_2023-07-20_12-33-rootfs.tar.zst"
old_sha256 = "29040c4dbcb01a4f78d261cecf49e71558150c0c661f0808b2ddc82f00612b5d"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2023-08-03_12-29-rootfs.tar.zst
# SHA256SUM=260bce37ea3f2c0122c6701ae48d1cb0a50e5a366c963ae80c3c199aa59703a9
# BUILD_DATE=20230803
# BUILD_TAG=2023-08-03
# STATUS=completed
# VERSION=latest02
# END_TIME=12:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-03
begin = 2023-08-03 12:02:36.442045330+00:00
start-sync_0 = 12:23:56
start-zstd = 12:25:49
start-sync_1 = 12:28:52
end-sync_1 = 12:29:11
end = 2023-08-03 12:29:11.733258127+00:00

[server]
repo = "cake233/kali-zsh-armv7"

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
ldd = 'ldd (Debian GLIBC 2.37-5) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabi)'
```
