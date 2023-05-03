# arch-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-amd64 \
    cake233/arch-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it arch-zsh-amd64 zsh
```

## arch-zsh-amd64.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2023-05-03"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_amd64_2023-05-03_00-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5c58c2061fbaaffaec9cbc6f059da0ff0b539c018325c17c46429a5567877d76"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1115930112

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "268M"
zstd_bytes = 280644962

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230426"
previous_tag = "2023-04-26"
previous_file = "arch-zsh_amd64_2023-04-26_00-17-rootfs.tar.zst"
previous_sha256 = "44ce53895cc672644e8c0879b800be7306d8035ac16866ffaf714e014d7c30a9"

current_version = "latest02"
current_date = "20230503"
old_file = "arch-zsh_amd64_2023-04-19_00-13-rootfs.tar.zst"
old_sha256 = "02bc2f43559fa9ecf052ceb95f6b6db27549c044e59c0e7db8468a73d7eda64b"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-zsh_amd64_2023-05-03_00-18-rootfs.tar.zst
# SHA256SUM=5c58c2061fbaaffaec9cbc6f059da0ff0b539c018325c17c46429a5567877d76
# BUILD_DATE=20230503
# BUILD_TAG=2023-05-03
# STATUS=completed
# VERSION=latest02
# END_TIME=00:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-03
begin = 2023-05-03 00:08:44.273959986+00:00
start-sync_0 = 00:12:14
start-zstd = 00:13:49
start-sync_1 = 00:18:27
end-sync_1 = 00:18:53
end = 2023-05-03 00:18:53.877085827+00:00

[server]
repo = "cake233/arch-zsh-amd64"

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
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
