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
tag = ["zsh", "2022-04-29"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_amd64_2022-04-29_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8ca8ccef1e59f68a2552009a320cefa3e8689873873baee16483208a74bd20d4"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1160159744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "259M"
zstd_bytes = 271556811

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220422"
previous_tag = "2022-04-22"
previous_file = "manjaro-zsh_amd64_2022-04-22_12-11-rootfs.tar.zst"
previous_sha256 = "2737301962323a4d6a531562ec5128d45b9da835e1ca0d450622f3e558b8ce1f"

current_version = "latest01"
current_date = "20220429"
old_file = "manjaro-zsh_amd64_2022-04-15_12-12-rootfs.tar.zst"
old_sha256 = "7b753e2eaa541d62a6f57f49ffa5ad2b50e1310bba265a1f1cf73ab3ffc8beba"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2022-04-29_12-12-rootfs.tar.zst
# SHA256SUM=8ca8ccef1e59f68a2552009a320cefa3e8689873873baee16483208a74bd20d4
# BUILD_DATE=20220429
# BUILD_TAG=2022-04-29
# STATUS=completed
# VERSION=latest01
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-29
begin = 2022-04-29 12:02:35.556719624+00:00
start-sync_0 = 12:04:50
start-zstd = 12:06:18
start-sync_1 = 12:11:47
end-sync_1 = 12:12:10
end = 2022-04-29 12:12:10.588990025+00:00

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
zsh = 'zsh 5.8.1 (x86_64-pc-linux-gnu)'
```
