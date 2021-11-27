# arch-zsh-arm64

## How to run it?

```shell
docker run \
    -it \
    --name arch-zsh-arm64 \
    cake233/arch-zsh-arm64
```

## How to exec shell?

```shell
    docker exec -it arch-zsh-arm64 zsh
```

## build info

```toml
[main]
name = "arch"
tag = ["zsh", "2021-11-27"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
nogui = true

# If the value is false, then the container will not be downloaded.
completed = true

[file]
name = "arch-zsh-arm64_2021-11-27_16-42.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "2d3ef8e81aa746a57f2427f966c6b4a2ae750070a519c436620216d02989d11b"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "960M"
tar-bytes = 1006012416

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "272M"
zstd-bytes = 284559956

[compatibility]
compatible_mode = true
rootfs_version = "latest01"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh-arm64_2021-11-27_16-42.tar.zst
# BUILD_DATE=20211127
# STATUS=completed
# VERSION=latest01
# END_TIME=16:42

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-27 16:33:05.129522938+00:00
start-sync_0 = 16:39:52
start-zstd = 16:41:34
start-sync_1 = 16:42:25
end-sync_1 = 16:42:49
end = 2021-11-27 16:42:49.151267850+00:00

[server]
name = "docker"
node = 4
repo = "cake233/arch-zsh-arm64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
