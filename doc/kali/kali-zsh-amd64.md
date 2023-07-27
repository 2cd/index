# kali-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-amd64 \
    cake233/kali-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it kali-zsh-amd64 zsh
```

## kali-zsh-amd64.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2023-07-27"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2023-07-27_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "660a417f916b81718f02be5d396caba51fa6f72a8d42e280d3d8648f3e095a9b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "775M"
tar_bytes = 812105216

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "151M"
zstd_bytes = 157522272

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230720"
previous_tag = "2023-07-20"
previous_file = "kali-zsh_amd64_2023-07-20_12-10-rootfs.tar.zst"
previous_sha256 = "a493f0e84bb51f945d363809b9cbed2ac6e7b5717e04d884d6af5331df214d92"

current_version = "latest02"
current_date = "20230727"
old_file = "kali-zsh_amd64_2023-07-13_12-09-rootfs.tar.zst"
old_sha256 = "6406ba03cf7e66073b1365671a70f135e7aee70b67c490d2aeadb8d56e3b1e2c"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2023-07-27_12-10-rootfs.tar.zst
# SHA256SUM=660a417f916b81718f02be5d396caba51fa6f72a8d42e280d3d8648f3e095a9b
# BUILD_DATE=20230727
# BUILD_TAG=2023-07-27
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-27
begin = 2023-07-27 12:02:32.658142242+00:00
start-sync_0 = 12:04:54
start-zstd = 12:06:48
start-sync_1 = 12:10:03
end-sync_1 = 12:10:21
end = 2023-07-27 12:10:21.777900000+00:00

[server]
repo = "cake233/kali-zsh-amd64"

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
ldd = 'ldd (Debian GLIBC 2.37-5) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
