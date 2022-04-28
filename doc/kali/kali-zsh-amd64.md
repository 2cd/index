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
tag = ["zsh", "2022-04-28"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2022-04-28_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "da69d00a5e3b1e282d9eec6536e0da3a2fdffd0f9e4a563017c94a1becb97257"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "747M"
tar_bytes = 782751232

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "145M"
zstd_bytes = 151259192

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220421"
previous_tag = "2022-04-21"
previous_file = "kali-zsh_amd64_2022-04-21_12-08-rootfs.tar.zst"
previous_sha256 = "742f4716ece3eeb7214eb4f5e88fa9533d8b8d7b1054721e1489bca18ccc873c"

current_version = "latest01"
current_date = "20220428"
old_file = "kali-zsh_amd64_2022-04-14_12-08-rootfs.tar.zst"
old_sha256 = "a7ebbc4f899462115a5bd128d52032f1047a3ac0745b7d6cc276492f3e2001ff"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2022-04-28_12-09-rootfs.tar.zst
# SHA256SUM=da69d00a5e3b1e282d9eec6536e0da3a2fdffd0f9e4a563017c94a1becb97257
# BUILD_DATE=20220428
# BUILD_TAG=2022-04-28
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-28
begin = 2022-04-28 12:02:31.110384999+00:00
start-sync_0 = 12:04:40
start-zstd = 12:06:29
start-sync_1 = 12:09:21
end-sync_1 = 12:09:36
end = 2022-04-28 12:09:36.559044934+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.8.1 (x86_64-debian-linux-gnu)'
```
