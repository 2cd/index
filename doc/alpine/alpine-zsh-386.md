# alpine-zsh-386

## How to run it?

```sh
docker run \
    -it \
    --name alpine-zsh-386 \
    cake233/alpine-zsh-386
```

## How to exec shell?

```sh
docker exec -it alpine-zsh-386 zsh
```

## alpine-zsh-386.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2024-02-15"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_i386_2024-02-15_00-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f542f83e4051bccd0b180647a6d38962eb822ca7122132a219e99016c317169e"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "126M"
tar_bytes = 131363328

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "41M"
zstd_bytes = 42115687

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231123"
previous_tag = "2023-11-23"
previous_file = "alpine-zsh_i386_2023-11-23_00-07-rootfs.tar.zst"
previous_sha256 = "13009352fc5a67ce689caa47e19f2cfc3ee2cbb3430536794de28aad2ea5109f"

current_version = "latest02"
current_date = "20240215"
old_file = "alpine-zsh_i386_2023-11-16_00-06-rootfs.tar.zst"
old_sha256 = "78b30eb67df00e983950ab9b46d35e9b662f327a8ce57e30cd5ee3c75e197560"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2024-02-15_00-07-rootfs.tar.zst
# SHA256SUM=f542f83e4051bccd0b180647a6d38962eb822ca7122132a219e99016c317169e
# BUILD_DATE=20240215
# BUILD_TAG=2024-02-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-15
begin = 2024-02-15 00:02:32.381883331+00:00
start-sync_0 = 00:05:06
start-zstd = 00:06:31
start-sync_1 = 00:07:08
end-sync_1 = 00:07:19
end = 2024-02-15 00:07:19.055427801+00:00

[server]
repo = "cake233/alpine-zsh-386"

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (i386) Version 1.2.4_git20230717'
zsh = 'zsh 5.9 (i586-alpine-linux-musl)'
```
