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
tag = ["zsh", "2022-11-29"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_amd64_2022-11-29_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2bf21845ae19c481d4081297bc29df07fb8f41dbbc36f9dd9dde66bfaf6e7e37"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1330933248

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "223M"
zstd_bytes = 233530379

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221122"
previous_tag = "2022-11-22"
previous_file = "fedora-zsh_amd64_2022-11-22_12-11-rootfs.tar.zst"
previous_sha256 = "84884caea81c4a8f0c402b44dc337a24a68c0e4742b87b85fe476ca54114f724"

current_version = "latest01"
current_date = "20221129"
old_file = "fedora-zsh_amd64_2022-11-15_12-11-rootfs.tar.zst"
old_sha256 = "9ed0a1820da9b6de03264b8f57e799d0ae305b00612d289d53afa095ddfafc5c"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2022-11-29_12-10-rootfs.tar.zst
# SHA256SUM=2bf21845ae19c481d4081297bc29df07fb8f41dbbc36f9dd9dde66bfaf6e7e37
# BUILD_DATE=20221129
# BUILD_TAG=2022-11-29
# STATUS=completed
# VERSION=latest01
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-29
begin = 2022-11-29 12:02:25.201076491+00:00
start-sync_0 = 12:04:22
start-zstd = 12:06:27
start-sync_1 = 12:10:34
end-sync_1 = 12:10:56
end = 2022-11-29 12:10:56.580624648+00:00

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
