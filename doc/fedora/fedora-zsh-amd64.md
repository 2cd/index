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
tag = ["zsh", "2022-04-12"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "fedora-zsh_amd64_2022-04-12_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "01aa7b7194128ce8d6b74b88e5c7fa219d1fe98f4715394c80ab41c6528ca015"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "951M"
tar_bytes = 997108736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "164M"
zstd_bytes = 171335447

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220405"
previous_tag = "2022-04-05"
previous_file = "fedora-zsh_amd64_2022-04-05_11-09-rootfs.tar.zst"
previous_sha256 = "2ab8acea7b1b3a8fead702a0f62eee9f9f266700e6dd245d3267120f7ee5b824"

current_version = "latest01"
current_date = "20220412"
old_file = "fedora-zsh_amd64_2022-03-29_11-14-rootfs.tar.zst"
old_sha256 = "0e35509f2a26da6ee9ea8563b95125f8fb6b79c53c7f1c326c15d5d6accd3a8e"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2022-04-12_12-09-rootfs.tar.zst
# SHA256SUM=01aa7b7194128ce8d6b74b88e5c7fa219d1fe98f4715394c80ab41c6528ca015
# BUILD_DATE=20220412
# BUILD_TAG=2022-04-12
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-12
begin = 2022-04-12 12:02:32.110067391+00:00
start-sync_0 = 12:04:16
start-zstd = 12:06:17
start-sync_1 = 12:09:27
end-sync_1 = 12:09:44
end = 2022-04-12 12:09:44.479377784+00:00

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.8.1 (x86_64-redhat-linux-gnu)'
```
