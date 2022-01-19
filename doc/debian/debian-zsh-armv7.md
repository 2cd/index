# debian-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-armv7 \
    cake233/debian-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it debian-zsh-armv7 zsh
```

## debian-zsh-armv7.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2022-01-19"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "debian-zsh_armhf_2022-01-19_12-20.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "620613203379b9793bdc64277e8d3a58feeb8133b37c9426663437b850ef46b3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "664M"
tar_bytes = 695243264

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "136M"
zstd_bytes = 142497590

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220119"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-zsh_armhf_2022-01-19_12-20-rootfs.tar.zst
# SHA256SUM=620613203379b9793bdc64277e8d3a58feeb8133b37c9426663437b850ef46b3
# BUILD_DATE=20220119
# BUILD_TAG=2022-01-19
# STATUS=completed
# VERSION=latest01
# END_TIME=12:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-19
begin = 2022-01-19 12:02:25.259543028+00:00
start-sync_0 = 12:15:53
start-zstd = 12:17:45
start-sync_1 = 12:19:52
end-sync_1 = 12:20:06
end = 2022-01-19 12:20:06.589873416+00:00

[server]
repo = "cake233/debian-zsh-armv7"

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
ldd = 'ldd (Debian GLIBC 2.33-3) 2.33'
zsh = 'zsh 5.8 (arm-unknown-linux-gnueabihf)'
```
