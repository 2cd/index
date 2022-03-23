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
tag = ["zsh", "2022-03-23"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "debian-zsh_amd64_2022-03-23_12-10.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "1dbf3d3219212f26bf4b42685d33a7b26b7a4f38d11b5dfd1e0a054054cb8ffe"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "744M"
tar_bytes = 779518976

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "144M"
zstd_bytes = 150033352

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220316"
previous_tag = "2022-03-16"
previous_file = "debian-zsh_amd64_2022-03-16_12-08-rootfs.tar.zst"
previous_sha256 = "78522ec5979b2c72f49b3f0fa4c404459f3a3bb7270a4d695745e90c4c556e13"

current_version = "latest02"
current_date = "20220323"
old_file = "debian-zsh_amd64_2022-03-09_12-08-rootfs.tar.zst"
old_sha256 = "acb9785f2109b1c3ddda9bc8e29665ecb40a7972f96eff99572b5b7bebdcaed7"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-zsh_amd64_2022-03-23_12-10-rootfs.tar.zst
# SHA256SUM=1dbf3d3219212f26bf4b42685d33a7b26b7a4f38d11b5dfd1e0a054054cb8ffe
# BUILD_DATE=20220323
# BUILD_TAG=2022-03-23
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-23
begin = 2022-03-23 12:02:40.311434725+00:00
start-sync_0 = 12:04:43
start-zstd = 12:06:38
start-sync_1 = 12:09:50
end-sync_1 = 12:10:05
end = 2022-03-23 12:10:05.263514292+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.8.1 (x86_64-debian-linux-gnu)'
```
