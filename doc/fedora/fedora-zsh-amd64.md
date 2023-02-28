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
tag = ["zsh", "2023-02-28"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_amd64_2023-02-28_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7657e1ba5f2692bc94b40ac98bb8cddb219bee15a492aadc72ef44bbfed2f5c7"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1351422976

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "227M"
zstd_bytes = 237470765

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230221"
previous_tag = "2023-02-21"
previous_file = "fedora-zsh_amd64_2023-02-21_12-12-rootfs.tar.zst"
previous_sha256 = "030262e7dfafa6f6e6d0e84c68dfc1a86d888dbec49f311860fb98bb0bb77b6b"

current_version = "latest02"
current_date = "20230228"
old_file = "fedora-zsh_amd64_2023-02-14_12-10-rootfs.tar.zst"
old_sha256 = "3805156d231d5336051648d140411a6590022b22e4a427d689dc1dd705f96f97"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2023-02-28_12-12-rootfs.tar.zst
# SHA256SUM=7657e1ba5f2692bc94b40ac98bb8cddb219bee15a492aadc72ef44bbfed2f5c7
# BUILD_DATE=20230228
# BUILD_TAG=2023-02-28
# STATUS=completed
# VERSION=latest02
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-28
begin = 2023-02-28 12:02:28.597984954+00:00
start-sync_0 = 12:04:46
start-zstd = 12:06:51
start-sync_1 = 12:12:04
end-sync_1 = 12:12:26
end = 2023-02-28 12:12:26.405587874+00:00

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'
```
