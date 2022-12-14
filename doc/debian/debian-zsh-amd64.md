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
tag = ["zsh", "2022-12-14"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_amd64_2022-12-14_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1d4627ff990ad67387a33120262028c88cde7eb05849d638f2ed249d2cfca293"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "765M"
tar_bytes = 801523200

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "147M"
zstd_bytes = 153896794

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221207"
previous_tag = "2022-12-07"
previous_file = "debian-zsh_amd64_2022-12-07_12-10-rootfs.tar.zst"
previous_sha256 = "7c276e95014a776ed82e6dc73978c9e7968ea58494a49bff26ab5901feb0f8ee"

current_version = "latest01"
current_date = "20221214"
old_file = "debian-zsh_amd64_2022-11-30_12-10-rootfs.tar.zst"
old_sha256 = "0e7f02097caa27af66907e5a9325f499862ce06feadb3ea8120b28ffe48b219e"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-zsh_amd64_2022-12-14_12-08-rootfs.tar.zst
# SHA256SUM=1d4627ff990ad67387a33120262028c88cde7eb05849d638f2ed249d2cfca293
# BUILD_DATE=20221214
# BUILD_TAG=2022-12-14
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-14
begin = 2022-12-14 12:02:22.582132381+00:00
start-sync_0 = 12:04:02
start-zstd = 12:05:49
start-sync_1 = 12:08:20
end-sync_1 = 12:08:34
end = 2022-12-14 12:08:34.093468925+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-6) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
