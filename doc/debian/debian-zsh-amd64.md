# debian-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-amd64 \
    cake233/debian-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it debian-zsh-amd64 zsh
```

## debian-zsh-amd64.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2022-11-09"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_amd64_2022-11-09_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b3785d6968e75dce7c2dd7d704b57fe967a59f4bb8ae76a4ec8202a0913027a7"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "761M"
tar_bytes = 797465088

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "147M"
zstd_bytes = 153670402

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221102"
previous_tag = "2022-11-02"
previous_file = "debian-zsh_amd64_2022-11-02_12-09-rootfs.tar.zst"
previous_sha256 = "0717a56c88044f5e797056a774ff511a990ec0e4a98ac65d070bee55dcf8121e"

current_version = "latest02"
current_date = "20221109"
old_file = "debian-zsh_amd64_2022-10-26_12-09-rootfs.tar.zst"
old_sha256 = "92d9d2b27599d698f5ece3f2dad86034e5b10e7e839ae426902321167197a368"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-zsh_amd64_2022-11-09_12-09-rootfs.tar.zst
# SHA256SUM=b3785d6968e75dce7c2dd7d704b57fe967a59f4bb8ae76a4ec8202a0913027a7
# BUILD_DATE=20221109
# BUILD_TAG=2022-11-09
# STATUS=completed
# VERSION=latest02
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-09
begin = 2022-11-09 12:02:24.401712735+00:00
start-sync_0 = 12:04:24
start-zstd = 12:06:11
start-sync_1 = 12:09:05
end-sync_1 = 12:09:19
end = 2022-11-09 12:09:20.022430165+00:00

[server]
repo = "cake233/debian-zsh-amd64"

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
ldd = 'ldd (Debian GLIBC 2.36-4) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
