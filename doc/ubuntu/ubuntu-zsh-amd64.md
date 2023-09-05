# ubuntu-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-zsh-amd64 \
    cake233/ubuntu-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it ubuntu-zsh-amd64 zsh
```

## ubuntu-zsh-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2023-09-05", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_amd64_2023-09-05_00-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7c9c33c30f349134cc8ef98f21aa92c85ee375eec18e8bf243b559d5c67c55c9"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "766M"
tar_bytes = 802219520

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "154M"
zstd_bytes = 161221891

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230905"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-zsh_amd64_2023-09-05_00-10-rootfs.tar.zst
# SHA256SUM=7c9c33c30f349134cc8ef98f21aa92c85ee375eec18e8bf243b559d5c67c55c9
# BUILD_DATE=20230905
# BUILD_TAG=2023-09-05
# STATUS=completed
# VERSION=latest01
# END_TIME=00:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-05
begin = 2023-09-05 00:02:41.104682632+00:00
start-sync_0 = 00:05:33
start-zstd = 00:07:26
start-sync_1 = 00:10:17
end-sync_1 = 00:10:37
end = 2023-09-05 00:10:37.712902793+00:00

[server]
repo = "cake233/ubuntu-zsh-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu4) 2.38'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'
```