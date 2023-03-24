# manjaro-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name manjaro-zsh-amd64 \
    cake233/manjaro-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it manjaro-zsh-amd64 zsh
```

## manjaro-zsh-amd64.toml

```toml
[main]
name = "manjaro"
tag = ["zsh", "2023-03-24"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_amd64_2023-03-24_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a2ea08dbc64ab7fe6bfeac042551df2514d2cb4b878f22f1409964ce8239df28"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1197425664

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "280M"
zstd_bytes = 292563715

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230317"
previous_tag = "2023-03-17"
previous_file = "manjaro-zsh_amd64_2023-03-17_12-12-rootfs.tar.zst"
previous_sha256 = "adb78c807150febdacaf4b3e261a4910810620855fbf49dc423cb8f284f4628b"

current_version = "latest02"
current_date = "20230324"
old_file = "manjaro-zsh_amd64_2023-03-10_12-12-rootfs.tar.zst"
old_sha256 = "1062d8cea3c8eb054468c7dc298937853460792fc6ecafb14017169225d94b72"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2023-03-24_12-12-rootfs.tar.zst
# SHA256SUM=a2ea08dbc64ab7fe6bfeac042551df2514d2cb4b878f22f1409964ce8239df28
# BUILD_DATE=20230324
# BUILD_TAG=2023-03-24
# STATUS=completed
# VERSION=latest02
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-24
begin = 2023-03-24 12:02:33.003142589+00:00
start-sync_0 = 12:05:08
start-zstd = 12:06:58
start-sync_1 = 12:12:06
end-sync_1 = 12:12:33
end = 2023-03-24 12:12:33.124696970+00:00

[server]
repo = "cake233/manjaro-zsh-amd64"

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
