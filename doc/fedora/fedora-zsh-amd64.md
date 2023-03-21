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
tag = ["zsh", "2023-03-21"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_amd64_2023-03-21_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "42ce8c5d5a4f8098ff9c870b8f8e7a207143e1a07a15b4db3fc83bcff95a5c45"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1352708608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "227M"
zstd_bytes = 237954472

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230314"
previous_tag = "2023-03-14"
previous_file = "fedora-zsh_amd64_2023-03-14_12-10-rootfs.tar.zst"
previous_sha256 = "6c8ba6e60809b6ff6c8be89ae1a9ac0a262891f545170b3531c616fbbccd4115"

current_version = "latest01"
current_date = "20230321"
old_file = "fedora-zsh_amd64_2023-03-07_12-13-rootfs.tar.zst"
old_sha256 = "21068f8dc8c7f5ef521a75bb95882f6328f1ca8edfd71e2eed91cce4630d1de4"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2023-03-21_12-11-rootfs.tar.zst
# SHA256SUM=42ce8c5d5a4f8098ff9c870b8f8e7a207143e1a07a15b4db3fc83bcff95a5c45
# BUILD_DATE=20230321
# BUILD_TAG=2023-03-21
# STATUS=completed
# VERSION=latest01
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-21
begin = 2023-03-21 12:02:30.072473469+00:00
start-sync_0 = 12:04:36
start-zstd = 12:06:41
start-sync_1 = 12:11:02
end-sync_1 = 12:11:22
end = 2023-03-21 12:11:22.295656476+00:00

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
ldd = 'ldd (GNU libc) 2.37.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'
```
