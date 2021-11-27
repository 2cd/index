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
platform = "linux/amd64"
nogui = true

# If the value is false, then the container will not be downloaded.
completed = true

[file]
name = "arch-zsh-amd64_2021-11-27_16-38.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "4af612ceced756a7131f128e424b9719399ad5cf11b85cca7c7d8c919e8f2ecb"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "975M"
tar-bytes = 1021849600

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "284M"
zstd-bytes = 296748735

[compatibility]
compatible_mode = true
rootfs_version = "latest02"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-zsh-amd64_2021-11-27_16-38.tar.zst
# BUILD_DATE=20211127
# STATUS=completed
# VERSION=latest02
# END_TIME=16:38

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-27 16:33:02.500104607+00:00
start-sync_0 = 16:35:09
start-zstd = 16:36:59
start-sync_1 = 16:37:43
end-sync_1 = 16:38:12
end = 2021-11-27 16:38:12.096767069+00:00

[server]
name = "docker"
node = 4
repo = "cake233/arch-zsh-amd64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
