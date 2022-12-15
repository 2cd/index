# alpine-zsh-386

## How to run it?

```sh
docker run \
    -it \
    --name alpine-zsh-386 \
    cake233/alpine-zsh-386
```

## How to exec shell?

```sh
docker exec -it alpine-zsh-386 zsh
```

## alpine-zsh-386.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2022-12-15"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_i386_2022-12-15_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f2a96fd3db57aa56b213d34ec5547066b1a765ed7acc11a32fa94183e62a1b5f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "92M"
tar_bytes = 96410112

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "30M"
zstd_bytes = 30907055

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221208"
previous_tag = "2022-12-08"
previous_file = "alpine-zsh_i386_2022-12-08_00-06-rootfs.tar.zst"
previous_sha256 = "330ef78435f6ce9e918b8e83041974390a423db3f66eff915b3beec9f3defbb5"

current_version = "latest02"
current_date = "20221215"
old_file = "alpine-zsh_i386_2022-12-01_00-06-rootfs.tar.zst"
old_sha256 = "a5d02a52181e2f5d4ae9db053e96b786d75fee42a30d16a59714649ca2206f05"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2022-12-15_00-06-rootfs.tar.zst
# SHA256SUM=f2a96fd3db57aa56b213d34ec5547066b1a765ed7acc11a32fa94183e62a1b5f
# BUILD_DATE=20221215
# BUILD_TAG=2022-12-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-15
begin = 2022-12-15 00:02:29.903552853+00:00
start-sync_0 = 00:04:39
start-zstd = 00:06:04
start-sync_1 = 00:06:36
end-sync_1 = 00:06:47
end = 2022-12-15 00:06:47.452771378+00:00

[server]
repo = "cake233/alpine-zsh-386"

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (i386) Version 1.2.3'
zsh = 'zsh 5.9 (i586-alpine-linux-musl)'
```
