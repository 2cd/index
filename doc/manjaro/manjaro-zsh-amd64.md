# manjaro-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name manjaro-zsh-amd64 \
    cake233/manjaro-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it manjaro-zsh-amd64 zsh
```

## manjaro-zsh-amd64.toml

```toml
[main]
name = "manjaro"
tag = ["zsh", "2023-04-14"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_amd64_2023-04-14_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c16ddbf6c5442d0b1a7ae360cab4da9ce641edc11e17b490ea3e87c8dc75fcd2"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1203058688

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "281M"
zstd_bytes = 293641497

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230407"
previous_tag = "2023-04-07"
previous_file = "manjaro-zsh_amd64_2023-04-07_12-11-rootfs.tar.zst"
previous_sha256 = "c8059452d9e83b832a413f42d61b9df06db957b1577d6f8092a0b6ee26b93c2e"

current_version = "latest01"
current_date = "20230414"
old_file = "manjaro-zsh_amd64_2023-03-31_12-13-rootfs.tar.zst"
old_sha256 = "8a99f733d8e55c07f06135426fc64a42fa544191f2e2de9bdcb590a9018134e5"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2023-04-14_12-11-rootfs.tar.zst
# SHA256SUM=c16ddbf6c5442d0b1a7ae360cab4da9ce641edc11e17b490ea3e87c8dc75fcd2
# BUILD_DATE=20230414
# BUILD_TAG=2023-04-14
# STATUS=completed
# VERSION=latest01
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-14
begin = 2023-04-14 12:02:26.951505278+00:00
start-sync_0 = 12:04:40
start-zstd = 12:06:24
start-sync_1 = 12:11:00
end-sync_1 = 12:11:23
end = 2023-04-14 12:11:23.527993876+00:00

[server]
repo = "cake233/manjaro-zsh-amd64"

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
