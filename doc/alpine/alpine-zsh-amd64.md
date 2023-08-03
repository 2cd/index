# alpine-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name alpine-zsh-amd64 \
    cake233/alpine-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it alpine-zsh-amd64 zsh
```

## alpine-zsh-amd64.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2023-08-03"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_amd64_2023-08-03_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "96ad3f2307045f25490a8687480aa5e8ece210116c7b4d2cb7f3af6a3973199a"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "130M"
tar_bytes = 135690752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "37M"
zstd_bytes = 38762704

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230727"
previous_tag = "2023-07-27"
previous_file = "alpine-zsh_amd64_2023-07-27_00-05-rootfs.tar.zst"
previous_sha256 = "fdac870cceee1e8d5757b3fe664ec900ded6c42de50c3a0ace6d422d5109d002"

current_version = "latest02"
current_date = "20230803"
old_file = "alpine-zsh_amd64_2023-07-20_00-05-rootfs.tar.zst"
old_sha256 = "93d04d27152bad55776c0408968b81a756af1c7d6b7dd48056506d48ee673e88"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-zsh_amd64_2023-08-03_00-05-rootfs.tar.zst
# SHA256SUM=96ad3f2307045f25490a8687480aa5e8ece210116c7b4d2cb7f3af6a3973199a
# BUILD_DATE=20230803
# BUILD_TAG=2023-08-03
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-03
begin = 2023-08-03 00:02:29.455091617+00:00
start-sync_0 = 00:03:14
start-zstd = 00:04:40
start-sync_1 = 00:05:35
end-sync_1 = 00:05:45
end = 2023-08-03 00:05:45.080686982+00:00

[server]
repo = "cake233/alpine-zsh-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.4_git20230717'
zsh = 'zsh 5.9 (x86_64-alpine-linux-musl)'
```
