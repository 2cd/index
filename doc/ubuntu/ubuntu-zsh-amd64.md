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
tag = ["zsh", "2022-09-27", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_amd64_2022-09-27_00-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "81361a82fcea22c6e4ea4190c1f2abfe2085783b0414262229253f7bef5020d1"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "688M"
tar_bytes = 721054720

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "133M"
zstd_bytes = 138808897

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220920"
previous_tag = "2022-09-20"
previous_file = "ubuntu-zsh_amd64_2022-09-20_00-09-rootfs.tar.zst"
previous_sha256 = "4d8212daf2b0d0c1bd4eb1448f77fdf777b974df190ecb21796c31a712dbbe17"

current_version = "latest01"
current_date = "20220927"
old_file = "ubuntu-zsh_amd64_2022-09-13_00-10-rootfs.tar.zst"
old_sha256 = "cbe5701400791830ab95ec038a1e25cc9b831d1f8f58668a6c98ad50aa673e5f"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-zsh_amd64_2022-09-27_00-08-rootfs.tar.zst
# SHA256SUM=81361a82fcea22c6e4ea4190c1f2abfe2085783b0414262229253f7bef5020d1
# BUILD_DATE=20220927
# BUILD_TAG=2022-09-27
# STATUS=completed
# VERSION=latest01
# END_TIME=00:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-27
begin = 2022-09-27 00:02:24.231599832+00:00
start-sync_0 = 00:04:22
start-zstd = 00:06:05
start-sync_1 = 00:08:19
end-sync_1 = 00:08:33
end = 2022-09-27 00:08:33.390631021+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu3) 2.36'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'
```
