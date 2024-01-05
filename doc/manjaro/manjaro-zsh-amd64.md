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
tag = ["zsh", "2024-01-05"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_amd64_2024-01-05_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "562a0ce3ff5bb7d6b93d4ef3401b8069badef565bd3395dc3956e9e6e3675a17"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1288919040

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "299M"
zstd_bytes = 312810715

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231124"
previous_tag = "2023-11-24"
previous_file = "manjaro-zsh_amd64_2023-11-24_12-10-rootfs.tar.zst"
previous_sha256 = "9557f25561203750d2572f11a170cc3c664349835ee3db4f43fe12592f3b102e"

current_version = "latest01"
current_date = "20240105"
old_file = "manjaro-zsh_amd64_2023-11-17_12-10-rootfs.tar.zst"
old_sha256 = "257534893add329939104780e715ce043d91e475e72423b6e9a227046722a2b1"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2024-01-05_12-10-rootfs.tar.zst
# SHA256SUM=562a0ce3ff5bb7d6b93d4ef3401b8069badef565bd3395dc3956e9e6e3675a17
# BUILD_DATE=20240105
# BUILD_TAG=2024-01-05
# STATUS=completed
# VERSION=latest01
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-05
begin = 2024-01-05 12:02:35.750651392+00:00
start-sync_0 = 12:04:50
start-zstd = 12:06:35
start-sync_1 = 12:10:19
end-sync_1 = 12:10:40
end = 2024-01-05 12:10:40.288525854+00:00

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
ldd = 'ldd (GNU libc) 2.38'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
