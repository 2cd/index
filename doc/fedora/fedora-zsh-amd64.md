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
tag = ["zsh", "2022-10-11"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_amd64_2022-10-11_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8104644914286dacaa2302bbf0c8b6bc18ee3e8a1c07fd94c7b58df6b9e4814f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1304891904

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "222M"
zstd_bytes = 231800945

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221004"
previous_tag = "2022-10-04"
previous_file = "fedora-zsh_amd64_2022-10-04_12-10-rootfs.tar.zst"
previous_sha256 = "63557ad9bdce69af6f365fbe2f8f9bac7d6e1ba8b4a33c02adc473b58899a50f"

current_version = "latest02"
current_date = "20221011"
old_file = "fedora-zsh_amd64_2022-09-27_12-11-rootfs.tar.zst"
old_sha256 = "d38c22407e9309efea73f7f6107a0baeee492679e2e0f072e7a49906dc014768"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2022-10-11_12-10-rootfs.tar.zst
# SHA256SUM=8104644914286dacaa2302bbf0c8b6bc18ee3e8a1c07fd94c7b58df6b9e4814f
# BUILD_DATE=20221011
# BUILD_TAG=2022-10-11
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-11
begin = 2022-10-11 12:02:19.789782703+00:00
start-sync_0 = 12:04:15
start-zstd = 12:06:19
start-sync_1 = 12:10:15
end-sync_1 = 12:10:35
end = 2022-10-11 12:10:35.590053015+00:00

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
