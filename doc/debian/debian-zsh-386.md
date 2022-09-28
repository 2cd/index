# debian-zsh-386

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-386 \
    cake233/debian-zsh-386
```

## How to exec shell?

```sh
docker exec -it debian-zsh-386 zsh
```

## debian-zsh-386.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2022-09-28"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_i386_2022-09-28_12-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f062795e1a12f2eec558e32107e38a7cfd3df065ffa5cd02d9b438dd57972e88"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "762M"
tar_bytes = 798157312

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "151M"
zstd_bytes = 157732755

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220921"
previous_tag = "2022-09-21"
previous_file = "debian-zsh_i386_2022-09-21_12-17-rootfs.tar.zst"
previous_sha256 = "73f16a45e963143a63468396f1c924db5e12864f82ac519f7ba7a4295e1cb4df"

current_version = "latest02"
current_date = "20220928"
old_file = "debian-zsh_i386_2022-09-14_12-18-rootfs.tar.zst"
old_sha256 = "594fe78a321abd40dfaf6f2872a0781779917b59cef5f087255d0ff4f3fa73aa"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-zsh_i386_2022-09-28_12-17-rootfs.tar.zst
# SHA256SUM=f062795e1a12f2eec558e32107e38a7cfd3df065ffa5cd02d9b438dd57972e88
# BUILD_DATE=20220928
# BUILD_TAG=2022-09-28
# STATUS=completed
# VERSION=latest02
# END_TIME=12:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-28
begin = 2022-09-28 12:02:22.513334138+00:00
start-sync_0 = 12:13:38
start-zstd = 12:15:24
start-sync_1 = 12:17:41
end-sync_1 = 12:17:55
end = 2022-09-28 12:17:55.714634466+00:00

[server]
repo = "cake233/debian-zsh-386"

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
ldd = 'ldd (Debian GLIBC 2.35-1) 2.35'
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'
```
