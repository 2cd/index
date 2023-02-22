# debian-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-amd64 \
    cake233/debian-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it debian-zsh-amd64 zsh
```

## debian-zsh-amd64.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2023-02-22"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_amd64_2023-02-22_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c398e7f03e534feb216308b73ab9a3ef17b5b38cc6b7138b5dacde463433f62f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "773M"
tar_bytes = 809944064

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "150M"
zstd_bytes = 156670386

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230215"
previous_tag = "2023-02-15"
previous_file = "debian-zsh_amd64_2023-02-15_12-09-rootfs.tar.zst"
previous_sha256 = "ffba61fb9c4c8f7456ec915b94c2988c2ebfc5c131d529d07cbb7654e9b15bf6"

current_version = "latest01"
current_date = "20230222"
old_file = "debian-zsh_amd64_2023-02-08_12-08-rootfs.tar.zst"
old_sha256 = "04b86c47bf7d6895075236ebde7b6bad6e75552a3bcf6df0cc01d5e2ed9ba4a5"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-zsh_amd64_2023-02-22_12-10-rootfs.tar.zst
# SHA256SUM=c398e7f03e534feb216308b73ab9a3ef17b5b38cc6b7138b5dacde463433f62f
# BUILD_DATE=20230222
# BUILD_TAG=2023-02-22
# STATUS=completed
# VERSION=latest01
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-22
begin = 2023-02-22 12:02:35.842709144+00:00
start-sync_0 = 12:04:36
start-zstd = 12:06:32
start-sync_1 = 12:09:46
end-sync_1 = 12:10:06
end = 2023-02-22 12:10:06.612249498+00:00

[server]
repo = "cake233/debian-zsh-amd64"

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
