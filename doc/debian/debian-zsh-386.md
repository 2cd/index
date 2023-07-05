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
tag = ["zsh", "2023-07-05"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_i386_2023-07-05_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9eb4425edd9ca0e9b67a161885b8f1c2a3eccf6bd3ecc71d3dc8316c79f0acbd"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "692M"
tar_bytes = 724969472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "133M"
zstd_bytes = 138893121

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230628"
previous_tag = "2023-06-28"
previous_file = "debian-zsh_i386_2023-06-28_12-18-rootfs.tar.zst"
previous_sha256 = "e13b7241dfa3272af600685c26fb04dfc98ac276d7e604063d91817021770cbf"

current_version = "latest02"
current_date = "20230705"
old_file = "debian-zsh_i386_2023-06-21_12-18-rootfs.tar.zst"
old_sha256 = "bf401fdb73495d81664905a43c2265e4f52372d07f7dc7cad6d1f46020ea721d"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-zsh_i386_2023-07-05_12-18-rootfs.tar.zst
# SHA256SUM=9eb4425edd9ca0e9b67a161885b8f1c2a3eccf6bd3ecc71d3dc8316c79f0acbd
# BUILD_DATE=20230705
# BUILD_TAG=2023-07-05
# STATUS=completed
# VERSION=latest02
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-05
begin = 2023-07-05 12:02:36.878446882+00:00
start-sync_0 = 12:14:51
start-zstd = 12:15:32
start-sync_1 = 12:18:26
end-sync_1 = 12:18:43
end = 2023-07-05 12:18:43.310581870+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-3) 2.37'
zsh = ''
```
