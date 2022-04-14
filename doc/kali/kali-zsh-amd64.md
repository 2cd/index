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
tag = ["zsh", "2022-04-14"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "kali-zsh_amd64_2022-04-14_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a7ebbc4f899462115a5bd128d52032f1047a3ac0745b7d6cc276492f3e2001ff"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "744M"
tar_bytes = 779698176

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "144M"
zstd_bytes = 150214679

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220407"
previous_tag = "2022-04-07"
previous_file = "kali-zsh_amd64_2022-04-07_11-08-rootfs.tar.zst"
previous_sha256 = "e3624c088c6aea7927acb168a4ad436cf13159509a9c581e18199246594fbba8"

current_version = "latest01"
current_date = "20220414"
old_file = "kali-zsh_amd64_2022-03-31_11-08-rootfs.tar.zst"
old_sha256 = "4f530fc9cc55426cd4ed2b35cc8543026e6d9a3554b25b9f909548d49900d2cc"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2022-04-14_12-08-rootfs.tar.zst
# SHA256SUM=a7ebbc4f899462115a5bd128d52032f1047a3ac0745b7d6cc276492f3e2001ff
# BUILD_DATE=20220414
# BUILD_TAG=2022-04-14
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-14
begin = 2022-04-14 12:02:30.634699138+00:00
start-sync_0 = 12:04:24
start-zstd = 12:06:12
start-sync_1 = 12:08:35
end-sync_1 = 12:08:51
end = 2022-04-14 12:08:51.384408378+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.8.1 (x86_64-debian-linux-gnu)'
```
