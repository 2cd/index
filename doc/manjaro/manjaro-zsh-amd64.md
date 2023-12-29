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
tag = ["zsh", "2023-12-29"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_amd64_2023-12-29_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c71855c60a793cd65cb7fecd11af902a94f5d12300eca24ba37a8c2f2c1b6182"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1288528896

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "299M"
zstd_bytes = 312753444

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231124"
previous_tag = "2023-11-24"
previous_file = "manjaro-zsh_amd64_2023-11-24_12-10-rootfs.tar.zst"
previous_sha256 = "9557f25561203750d2572f11a170cc3c664349835ee3db4f43fe12592f3b102e"

current_version = "latest01"
current_date = "20231229"
old_file = "manjaro-zsh_amd64_2023-11-17_12-10-rootfs.tar.zst"
old_sha256 = "257534893add329939104780e715ce043d91e475e72423b6e9a227046722a2b1"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2023-12-29_12-09-rootfs.tar.zst
# SHA256SUM=c71855c60a793cd65cb7fecd11af902a94f5d12300eca24ba37a8c2f2c1b6182
# BUILD_DATE=20231229
# BUILD_TAG=2023-12-29
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-29
begin = 2023-12-29 12:02:32.228810217+00:00
start-sync_0 = 12:04:20
start-zstd = 12:05:54
start-sync_1 = 12:09:41
end-sync_1 = 12:09:59
end = 2023-12-29 12:09:59.177972894+00:00

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
