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
tag = ["zsh", "2022-03-29"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "fedora-zsh_amd64_2022-03-29_11-14.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "0e35509f2a26da6ee9ea8563b95125f8fb6b79c53c7f1c326c15d5d6accd3a8e"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "961M"
tar_bytes = 1007385088

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "165M"
zstd_bytes = 172157375

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220322"
previous_tag = "2022-03-22"
previous_file = "fedora-zsh_amd64_2022-03-22_12-10-rootfs.tar.zst"
previous_sha256 = "0c627f695ac004bd785c7c27973707f8b443dd185b6258ddacf9caaed730509a"

current_version = "latest01"
current_date = "20220329"
old_file = "fedora-zsh_amd64_2022-03-15_12-10-rootfs.tar.zst"
old_sha256 = "3380c691554de1962cd21a1cdc483d638c5a3101fed87875bb9a2b14531662a9"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2022-03-29_11-14-rootfs.tar.zst
# SHA256SUM=0e35509f2a26da6ee9ea8563b95125f8fb6b79c53c7f1c326c15d5d6accd3a8e
# BUILD_DATE=20220329
# BUILD_TAG=2022-03-29
# STATUS=completed
# VERSION=latest01
# END_TIME=11:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-29
begin = 2022-03-29 11:06:29.243596470+00:00
start-sync_0 = 11:08:27
start-zstd = 11:10:30
start-sync_1 = 11:14:10
end-sync_1 = 11:14:28
end = 2022-03-29 11:14:28.836939057+00:00

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
