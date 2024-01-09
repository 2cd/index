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
tag = ["zsh", "2024-01-09", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_amd64_2024-01-09_00-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b91f2b60e0d394e358dc9c104c2e10e4526bbfa0a0567f6d55c1e1aecd4f0388"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "729M"
tar_bytes = 763928064

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "145M"
zstd_bytes = 151927449

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231128"
previous_tag = "2023-11-28"
previous_file = "ubuntu-zsh_amd64_2023-11-28_00-09-rootfs.tar.zst"
previous_sha256 = "5798dea8c157f1f728d0cf05daa9da172f6184b6a4d083dbdbdfeb68824165a3"

current_version = "latest02"
current_date = "20240109"
old_file = "ubuntu-zsh_amd64_2023-11-21_00-08-rootfs.tar.zst"
old_sha256 = "81fc9b6dee9587b6fd3bf5eb6936a5ffd26c2fab9c6c74388cb082f8b1497bbb"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-zsh_amd64_2024-01-09_00-09-rootfs.tar.zst
# SHA256SUM=b91f2b60e0d394e358dc9c104c2e10e4526bbfa0a0567f6d55c1e1aecd4f0388
# BUILD_DATE=20240109
# BUILD_TAG=2024-01-09
# STATUS=completed
# VERSION=latest02
# END_TIME=00:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-09
begin = 2024-01-09 00:02:33.457865600+00:00
start-sync_0 = 00:05:53
start-zstd = 00:07:32
start-sync_1 = 00:09:38
end-sync_1 = 00:09:53
end = 2024-01-09 00:09:54.004086118+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.38-3ubuntu1) 2.38'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'
```
