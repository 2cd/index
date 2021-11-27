# arch-zsh-amd64

## How to run it?

```shell
docker run \
    -it \
    --name arch-zsh-amd64 \
    cake233/arch-zsh-amd64
```

## How to exec shell?

```shell
    docker exec -it arch-zsh-amd64 zsh
```

## build info

```toml
[main]
name = "arch"
tag = ["zsh", "2021-11-27"]
os = "arch"
release = "latest"
arch = "amd64"
nogui = true

# If the value is false, then the container will not be downloaded.
completed = true

[file]
name = "arch-zsh-amd64_2021-11-27_13-24.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "9c49d04ef6f64c9f28b7477209bed5084102a479f6879bed357d42b64657f2d0"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "975M"
tar-bytes = 1021882880

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "284M"
zstd-bytes = 297315261

[compatibility]
compatible_mode = true
rootfs_version = "latest02"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-zsh-amd64_2021-11-27_13-24.tar.zst
# BUILD_DATE=20211127
# STATUS=completed
# VERSION=latest02
# END_TIME=13:24

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-27 13:19:42.485719709+00:00
start-sync_0 = 13:21:31
start-zstd = 13:23:15
start-sync_1 = 13:24:05
end-sync_1 = 13:24:30
end = 2021-11-27 13:24:30.599041618+00:00

[server]
name = "docker"
node = 4
repo = "cake233/arch-zsh-amd64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
