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
tag = ["zsh", "2023-05-10"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_amd64_2023-05-10_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c66ef3145601bae258ee6eb20c147a5d6736d2ac9a587eb9db5ef1862bd58015"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "774M"
tar_bytes = 810893824

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "150M"
zstd_bytes = 156914785

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230503"
previous_tag = "2023-05-03"
previous_file = "debian-zsh_amd64_2023-05-03_12-08-rootfs.tar.zst"
previous_sha256 = "a790e8ed05db0c54dbf32bb0d63a6cda33b7152882b52da1ea202261fe673fb1"

current_version = "latest02"
current_date = "20230510"
old_file = "debian-zsh_amd64_2023-04-26_12-10-rootfs.tar.zst"
old_sha256 = "1bf5dcebf9ac8507df677070e118d9b8a3a00e24b2a01c9e02383caac062efce"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-zsh_amd64_2023-05-10_12-09-rootfs.tar.zst
# SHA256SUM=c66ef3145601bae258ee6eb20c147a5d6736d2ac9a587eb9db5ef1862bd58015
# BUILD_DATE=20230510
# BUILD_TAG=2023-05-10
# STATUS=completed
# VERSION=latest02
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-10
begin = 2023-05-10 12:02:33.611795486+00:00
start-sync_0 = 12:04:36
start-zstd = 12:06:27
start-sync_1 = 12:09:31
end-sync_1 = 12:09:47
end = 2023-05-10 12:09:47.817133952+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
