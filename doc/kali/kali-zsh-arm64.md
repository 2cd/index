# kali-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-arm64 \
    cake233/kali-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it kali-zsh-arm64 zsh
```

## kali-zsh-arm64.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2022-10-20"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_arm64_2022-10-20_12-19.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9fcec1d4fa175ed950922707f43966b7fe3dbb4db197f2f676f98af223cb0c9c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "794M"
tar_bytes = 831796224

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "146M"
zstd_bytes = 152284561

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221013"
previous_tag = "2022-10-13"
previous_file = "kali-zsh_arm64_2022-10-13_12-20-rootfs.tar.zst"
previous_sha256 = "9aebf0c3ae0af06d7ebdd66925bf09dc8bdcc1a29e82507dbb074a98d7031b31"

current_version = "latest02"
current_date = "20221020"
old_file = "kali-zsh_arm64_2022-10-06_12-17-rootfs.tar.zst"
old_sha256 = "fa23ea754b95e6242ce542bf587d74f4e5fcee41708d28e8a9c186126fd15939"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-zsh_arm64_2022-10-20_12-19-rootfs.tar.zst
# SHA256SUM=9fcec1d4fa175ed950922707f43966b7fe3dbb4db197f2f676f98af223cb0c9c
# BUILD_DATE=20221020
# BUILD_TAG=2022-10-20
# STATUS=completed
# VERSION=latest02
# END_TIME=12:19

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-20
begin = 2022-10-20 12:02:26.661166239+00:00
start-sync_0 = 12:15:17
start-zstd = 12:17:02
start-sync_1 = 12:19:27
end-sync_1 = 12:19:42
end = 2022-10-20 12:19:42.271690963+00:00

[server]
repo = "cake233/kali-zsh-arm64"

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
ldd = 'ldd (Debian GLIBC 2.35-3) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
