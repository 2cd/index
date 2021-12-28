# fedora-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name fedora-zsh-amd64 \
    cake233/fedora-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it fedora-zsh-amd64 zsh
```

## fedora-zsh-amd64.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2021-12-28"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "fedora-zsh_amd64_2021-12-28_12-10.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "f7bb72f727d12d3b4cfae60a7d05ac8031fd93f012429e8c1c013fef1b48ad88"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "960M"
tar_bytes = 1005706240

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "164M"
zstd_bytes = 171125760

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211221"
previous_tag = "2021-12-21"
previous_file = "fedora-zsh_amd64_2021-12-21_12-10-rootfs.tar.zst"
previous_sha256 = "622acdea92a3b7b64cddeba11c66f1ddfccbfc723bcf0af86354f5173d2aac9c"

current_version = "latest01"
current_date = "20211228"
old_file = "fedora-zsh_amd64_2021-12-14_12-11-rootfs.tar.zst"
old_sha256 = "acef679771d1c70f0120d40d557c4e07495e5e1255ef6335091b650a4b2ecd77"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2021-12-28_12-10-rootfs.tar.zst
# SHA256SUM=f7bb72f727d12d3b4cfae60a7d05ac8031fd93f012429e8c1c013fef1b48ad88
# BUILD_DATE=20211228
# BUILD_TAG=2021-12-28
# STATUS=completed
# VERSION=latest01
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-28
begin = 2021-12-28 12:02:25.876512513+00:00
start-sync_0 = 12:04:17
start-zstd = 12:06:24
start-sync_1 = 12:09:59
end-sync_1 = 12:10:16
end = 2021-12-28 12:10:16.696906489+00:00

[server]
repo = "cake233/fedora-zsh-amd64"

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
ldd = 'ldd (GNU libc) 2.34.9000'
zsh = 'zsh 5.8 (x86_64-redhat-linux-gnu)'
```
