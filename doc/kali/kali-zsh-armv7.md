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
tag = ["zsh", "2023-11-09"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_armhf_2023-11-09_12-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3ceb79c77da2999d5bc28533a70adabcedf9216c88a7b3df1bf1629889f4ba7e"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "740M"
tar_bytes = 775625216

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "146M"
zstd_bytes = 152042257

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231026"
previous_tag = "2023-10-26"
previous_file = "kali-zsh_armhf_2023-10-26_12-24-rootfs.tar.zst"
previous_sha256 = "fe442ee0b144a0513859e3bbfc7c2c64bfdb80169dbe6a507dab66ce76dec825"

current_version = "latest01"
current_date = "20231109"
old_file = "kali-zsh_armhf_2023-10-19_12-30-rootfs.tar.zst"
old_sha256 = "7d6f22770aceffba287490ae5e8aade713bdf0a2bc5ff1b2c061a5e6d23bb8f8"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2023-11-09_12-28-rootfs.tar.zst
# SHA256SUM=3ceb79c77da2999d5bc28533a70adabcedf9216c88a7b3df1bf1629889f4ba7e
# BUILD_DATE=20231109
# BUILD_TAG=2023-11-09
# STATUS=completed
# VERSION=latest01
# END_TIME=12:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-09
begin = 2023-11-09 12:02:35.386207109+00:00
start-sync_0 = 12:23:13
start-zstd = 12:25:05
start-sync_1 = 12:27:42
end-sync_1 = 12:28:01
end = 2023-11-09 12:28:01.767423910+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabi)'
```
