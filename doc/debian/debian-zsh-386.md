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
tag = ["zsh", "2023-08-09"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_i386_2023-08-09_12-19.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9f898350c72a74de0aa82a3e129dd7229f6531d532fd63bec7aa495427592135"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "781M"
tar_bytes = 818889728

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "155M"
zstd_bytes = 162193590

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230802"
previous_tag = "2023-08-02"
previous_file = "debian-zsh_i386_2023-08-02_12-22-rootfs.tar.zst"
previous_sha256 = "444e37bbb63dd76a4e9214d6bbcfd145152dd38c762b15bb10e229b6e02ea300"

current_version = "latest01"
current_date = "20230809"
old_file = "debian-zsh_i386_2023-07-26_12-22-rootfs.tar.zst"
old_sha256 = "2dbff77069903479573ec82ed39dbbb2d724b3fc274a1e0a5e28db344e8e0728"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-zsh_i386_2023-08-09_12-19-rootfs.tar.zst
# SHA256SUM=9f898350c72a74de0aa82a3e129dd7229f6531d532fd63bec7aa495427592135
# BUILD_DATE=20230809
# BUILD_TAG=2023-08-09
# STATUS=completed
# VERSION=latest01
# END_TIME=12:19

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-09
begin = 2023-08-09 12:02:34.012782961+00:00
start-sync_0 = 12:14:16
start-zstd = 12:16:02
start-sync_1 = 12:18:44
end-sync_1 = 12:19:01
end = 2023-08-09 12:19:01.578033355+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'
```
