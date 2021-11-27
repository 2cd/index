# code-amd64

## How to run it?

```shell
docker run \
    -it \
    --name code-amd64 \
    cake233/code-amd64
```

## How to exec shell?

```shell
    docker exec -it code-amd64 bash
```

## build info

```toml
[main]
name = "code"
tag = ["latest", "2021-11-27", "vsc", "vscode", "online"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
nogui = true

# If the value is false, then the container will not be downloaded.
completed = true

[file]
name = "code-amd64_2021-11-27_17-47.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "396452bc47d942fecc91b21c6612b216427417c055338ee97eef8fd51109ebbc"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "517M"
tar-bytes = 541172224

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "128M"
zstd-bytes = 133841519

[compatibility]
compatible_mode = true
rootfs_version = "latest02"
# edition 2021
# DISTRO_NAME=debian_amd64
# ROOTFS_FILE=code-amd64_2021-11-27_17-47.tar.zst
# BUILD_DATE=20211127
# STATUS=completed
# VERSION=latest02
# END_TIME=17:47

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-27 17:44:56.032452510+00:00
start-sync_0 = 17:45:44
start-zstd = 17:46:21
start-sync_1 = 17:46:57
end-sync_1 = 17:47:11
end = 2021-11-27 17:47:11.083702470+00:00

[server]
name = "docker"
node = 4
repo = "cake233/code-amd64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
CODE_VERSION='3.12.0 b37ff28a0a582aee84a8f961755d0cb40a4081db'
```
