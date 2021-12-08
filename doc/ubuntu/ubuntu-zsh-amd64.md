# ubuntu-zsh-amd64

## How to run it?

```shell
docker run \
    -it \
    --name ubuntu-zsh-amd64 \
    cake233/ubuntu-zsh-amd64
```

## How to exec shell?

```shell
    docker exec -it ubuntu-zsh-amd64 zsh
```

## ubuntu-zsh-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2021-12-07", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "ubuntu-zsh_amd64_2021-12-07_00-08.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "e600abeff7f96c357a3a951ed19ef7844eda7ee6ec34c2d150b49ad871ebafae"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "626M"
tar_bytes = 656338944

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "111M"
zstd_bytes = 115587727

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211130"
previous_tag = "2021-11-30"
previous_file = "ubuntu-zsh_amd64_2021-11-30_00-08-rootfs.tar.zst"
previous_sha256 = ""

current_version = "latest02"
current_date = "20211207"
old_file = "ubuntu-zsh_amd64_2021-11-30_13-32-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-zsh_amd64_2021-12-07_00-08-rootfs.tar.zst
# SHA256SUM=e600abeff7f96c357a3a951ed19ef7844eda7ee6ec34c2d150b49ad871ebafae
# BUILD_DATE=20211207
# BUILD_TAG=2021-12-07
# STATUS=completed
# VERSION=latest02
# END_TIME=00:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-07
begin = 2021-12-07 00:02:21.422142645+00:00
start-sync_0 = 00:03:58
start-zstd = 00:05:38
start-sync_1 = 00:07:59
end-sync_1 = 00:08:12
end = 2021-12-07 00:08:12.119298111+00:00

[server]
repo = "cake233/ubuntu-zsh-amd64"

[server.node1]
name = "cn"
current = false
previous = true
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
```
