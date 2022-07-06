# arch-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-amd64 \
    cake233/arch-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it arch-zsh-amd64 zsh
```

## arch-zsh-amd64.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2022-07-06"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_amd64_2022-07-06_00-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "da3e057a7eff510f2eb8709e9048316c6db3f3edabd6cf721c5c979fb0edd1a6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "979M"
tar_bytes = 1026010112

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "247M"
zstd_bytes = 258458443

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220629"
previous_tag = "2022-06-29"
previous_file = "arch-zsh_amd64_2022-06-29_00-15-rootfs.tar.zst"
previous_sha256 = "4446b42f97a2876f635b3a8a80c08bfc053342fdfe3731dd5f9bd4b59613f68b"

current_version = "latest01"
current_date = "20220706"
old_file = "arch-zsh_amd64_2022-06-22_00-16-rootfs.tar.zst"
old_sha256 = "345c95ce55561182adc1ae3aa59b65aaf6e6824ca01e953eb452485324ddd48f"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-zsh_amd64_2022-07-06_00-16-rootfs.tar.zst
# SHA256SUM=da3e057a7eff510f2eb8709e9048316c6db3f3edabd6cf721c5c979fb0edd1a6
# BUILD_DATE=20220706
# BUILD_TAG=2022-07-06
# STATUS=completed
# VERSION=latest01
# END_TIME=00:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-06
begin = 2022-07-06 00:07:48.339552239+00:00
start-sync_0 = 00:11:51
start-zstd = 00:13:19
start-sync_1 = 00:16:36
end-sync_1 = 00:16:56
end = 2022-07-06 00:16:56.037441336+00:00

[server]
repo = "cake233/arch-zsh-amd64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
