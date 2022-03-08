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
tag = ["zsh", "2022-03-08", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "ubuntu-zsh_amd64_2022-03-08_00-08.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "7c70c7ab139d089644f1e6a80172151ff8230ba3cdf83cb63786cdd3bec1c04f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "636M"
tar_bytes = 666849792

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "114M"
zstd_bytes = 118644620

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220301"
previous_tag = "2022-03-01"
previous_file = "ubuntu-zsh_amd64_2022-03-01_00-07-rootfs.tar.zst"
previous_sha256 = "074e193fca47a3862ef003e8329dc97e2cfa7daff12c8051069b7c57fbe4d376"

current_version = "latest01"
current_date = "20220308"
old_file = "ubuntu-zsh_amd64_2022-02-22_00-09-rootfs.tar.zst"
old_sha256 = "11aa44d7fb1c8bc067bb148deefd47ef2505ae1df45bac5a29c7bf25f4d60db5"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-zsh_amd64_2022-03-08_00-08-rootfs.tar.zst
# SHA256SUM=7c70c7ab139d089644f1e6a80172151ff8230ba3cdf83cb63786cdd3bec1c04f
# BUILD_DATE=20220308
# BUILD_TAG=2022-03-08
# STATUS=completed
# VERSION=latest01
# END_TIME=00:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-08
begin = 2022-03-08 00:02:28.856744531+00:00
start-sync_0 = 00:04:24
start-zstd = 00:06:11
start-sync_1 = 00:08:40
end-sync_1 = 00:08:52
end = 2022-03-08 00:08:52.988151558+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu1) 2.35'
zsh = 'zsh 5.8.1 (x86_64-ubuntu-linux-gnu)'
```
