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
tag = ["zsh", "2024-01-23"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_amd64_2024-01-23_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "19a3701d1cf7467febec37724528657eda4593080f548ae88cc387317d742462"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1380104704

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "236M"
zstd_bytes = 246914400

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231121"
previous_tag = "2023-11-21"
previous_file = "fedora-zsh_amd64_2023-11-21_12-10-rootfs.tar.zst"
previous_sha256 = "b43d40d283dfa9b330411c8f80bb7c0a98973e373e796dc5c92aa5f523deca53"

current_version = "latest02"
current_date = "20240123"
old_file = "fedora-zsh_amd64_2023-11-14_12-09-rootfs.tar.zst"
old_sha256 = "a01be11bbf3c0e39592392a231a037949be299e60fba3af3310bbd546dd37ded"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2024-01-23_12-10-rootfs.tar.zst
# SHA256SUM=19a3701d1cf7467febec37724528657eda4593080f548ae88cc387317d742462
# BUILD_DATE=20240123
# BUILD_TAG=2024-01-23
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-23
begin = 2024-01-23 12:02:34.519208506+00:00
start-sync_0 = 12:04:24
start-zstd = 12:06:12
start-sync_1 = 12:09:52
end-sync_1 = 12:10:08
end = 2024-01-23 12:10:08.143539123+00:00

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
ldd = 'ldd (GNU libc) 2.38.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'
```
