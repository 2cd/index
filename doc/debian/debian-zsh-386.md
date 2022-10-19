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
tag = ["zsh", "2022-10-19"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_i386_2022-10-19_12-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e421a0dc54296feace22405726d49d4267c1f13403ea024deb8393d66fd9b086"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "646M"
tar_bytes = 677368832

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "122M"
zstd_bytes = 127721370

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221012"
previous_tag = "2022-10-12"
previous_file = "debian-zsh_i386_2022-10-12_12-19-rootfs.tar.zst"
previous_sha256 = "751fcd50f50538bc912f7acdf1c5344fee3321c71e1d18a7cd394c6b53e2ce74"

current_version = "latest01"
current_date = "20221019"
old_file = "debian-zsh_i386_2022-10-05_12-20-rootfs.tar.zst"
old_sha256 = "9caa56e03c74beba8998c93ff5e76b2b828daacab9d844f3b253238f99220139"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-zsh_i386_2022-10-19_12-16-rootfs.tar.zst
# SHA256SUM=e421a0dc54296feace22405726d49d4267c1f13403ea024deb8393d66fd9b086
# BUILD_DATE=20221019
# BUILD_TAG=2022-10-19
# STATUS=completed
# VERSION=latest01
# END_TIME=12:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-19
begin = 2022-10-19 12:02:30.216694761+00:00
start-sync_0 = 12:13:34
start-zstd = 12:14:13
start-sync_1 = 12:16:36
end-sync_1 = 12:16:53
end = 2022-10-19 12:16:53.296258904+00:00

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
ldd = 'ldd (Debian GLIBC 2.35-3) 2.35'
zsh = ''
```
