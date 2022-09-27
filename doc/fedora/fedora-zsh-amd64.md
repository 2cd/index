# fedora-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name fedora-zsh-amd64 \
    cake233/fedora-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it fedora-zsh-amd64 zsh
```

## fedora-zsh-amd64.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2022-09-27"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_amd64_2022-09-27_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d38c22407e9309efea73f7f6107a0baeee492679e2e0f072e7a49906dc014768"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1316478976

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "222M"
zstd_bytes = 232086304

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220920"
previous_tag = "2022-09-20"
previous_file = "fedora-zsh_amd64_2022-09-20_12-10-rootfs.tar.zst"
previous_sha256 = "2c82ca070c8892aecd92eae4ecbbe36271795da6e6bd298760bd946119107bf6"

current_version = "latest02"
current_date = "20220927"
old_file = "fedora-zsh_amd64_2022-09-13_12-11-rootfs.tar.zst"
old_sha256 = "2c846d1d08ece0f8cb19adb908e186080fca7a89db4508114b42dfe61af22776"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2022-09-27_12-11-rootfs.tar.zst
# SHA256SUM=d38c22407e9309efea73f7f6107a0baeee492679e2e0f072e7a49906dc014768
# BUILD_DATE=20220927
# BUILD_TAG=2022-09-27
# STATUS=completed
# VERSION=latest02
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-27
begin = 2022-09-27 12:02:22.733599455+00:00
start-sync_0 = 12:04:40
start-zstd = 12:06:48
start-sync_1 = 12:10:56
end-sync_1 = 12:11:16
end = 2022-09-27 12:11:16.189877358+00:00

[server]
repo = "cake233/fedora-zsh-amd64"

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'
```
