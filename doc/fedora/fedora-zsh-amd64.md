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
tag = ["zsh", "2022-10-18"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_amd64_2022-10-18_12-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "828911f3b52c87d89e5d8a1f7bdb80d42cd65408966fac71575ef22517339eb8"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1317163520

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "222M"
zstd_bytes = 232406977

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221011"
previous_tag = "2022-10-11"
previous_file = "fedora-zsh_amd64_2022-10-11_12-10-rootfs.tar.zst"
previous_sha256 = "8104644914286dacaa2302bbf0c8b6bc18ee3e8a1c07fd94c7b58df6b9e4814f"

current_version = "latest01"
current_date = "20221018"
old_file = "fedora-zsh_amd64_2022-10-04_12-10-rootfs.tar.zst"
old_sha256 = "63557ad9bdce69af6f365fbe2f8f9bac7d6e1ba8b4a33c02adc473b58899a50f"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2022-10-18_12-13-rootfs.tar.zst
# SHA256SUM=828911f3b52c87d89e5d8a1f7bdb80d42cd65408966fac71575ef22517339eb8
# BUILD_DATE=20221018
# BUILD_TAG=2022-10-18
# STATUS=completed
# VERSION=latest01
# END_TIME=12:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-18
begin = 2022-10-18 12:02:48.187253830+00:00
start-sync_0 = 12:06:06
start-zstd = 12:08:24
start-sync_1 = 12:13:29
end-sync_1 = 12:13:56
end = 2022-10-18 12:13:56.144526100+00:00

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'
```
