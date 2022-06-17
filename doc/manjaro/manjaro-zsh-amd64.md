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
tag = ["zsh", "2022-06-17"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_amd64_2022-06-17_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ade6ec5f9b6caa38a670bf0f9b5e2b434c8c8daee790aab2ac3fb501b1d587b7"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1181024256

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "269M"
zstd_bytes = 281520309

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220610"
previous_tag = "2022-06-10"
previous_file = "manjaro-zsh_amd64_2022-06-10_12-12-rootfs.tar.zst"
previous_sha256 = "871f81a7880ca7ca7ac8f22599ba9a3841a388d3b7cbd70d02861f65cfb7415c"

current_version = "latest02"
current_date = "20220617"
old_file = "manjaro-zsh_amd64_2022-06-03_12-10-rootfs.tar.zst"
old_sha256 = "eb4402b4193c9369c367f4da03b590af1f9b95eb2bd68e8ed603498ce9ed8b38"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2022-06-17_12-12-rootfs.tar.zst
# SHA256SUM=ade6ec5f9b6caa38a670bf0f9b5e2b434c8c8daee790aab2ac3fb501b1d587b7
# BUILD_DATE=20220617
# BUILD_TAG=2022-06-17
# STATUS=completed
# VERSION=latest02
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-17
begin = 2022-06-17 12:02:35.878150415+00:00
start-sync_0 = 12:05:01
start-zstd = 12:06:46
start-sync_1 = 12:12:13
end-sync_1 = 12:12:38
end = 2022-06-17 12:12:38.486883260+00:00

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
