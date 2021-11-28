# fedora-zsh-amd64

## How to run it?

```shell
docker run \
    -it \
    --name fedora-zsh-amd64 \
    cake233/fedora-zsh-amd64
```

## How to exec shell?

```shell
    docker exec -it fedora-zsh-amd64 zsh
```

## fedora-zsh-amd64.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2021-11-28"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "fedora-zsh-amd64_2021-11-28_13-53.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "6ba274de7be79c1f677961444bc9f375a453897782b831492961b2b4e7a559bd"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1210384384

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "294M"
zstd_bytes = 307234387

[compatibility]
compatible_mode = true
current_version = "latest01"
current_date = 20211128
last_version = "latest02"
last_date = 20211102
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh-amd64_2021-11-28_13-53.tar.zst
# BUILD_DATE=20211128
# STATUS=completed
# VERSION=latest01
# END_TIME=13:53

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-28 13:47:46.624520519+00:00
start-sync_0 = 13:49:46
start-zstd = 13:51:52
start-sync_1 = 13:52:51
end-sync_1 = 13:53:18
end = 2021-11-28 13:53:18.293374732+00:00

[server]
repo = "cake233/fedora-zsh-amd64"

[server.node1]
name = "cn"
current = false
last = true
split = false

[server.node2]
name = "us"
current = false
last = false
split = false
part = 12

[server.node3]
name = "global"
current = false
last = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
