# ubuntu-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-zsh-arm64 \
    cake233/ubuntu-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it ubuntu-zsh-arm64 zsh
```

## ubuntu-zsh-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2022-04-27", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_arm64_2022-04-27_13-30.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "052f502307777a7742d03966df288d04d43ae90bfe8c6bc9731cc91cb59d122b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "619M"
tar_bytes = 648553472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "111M"
zstd_bytes = 115950828

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220426"
previous_tag = "2022-04-26"
previous_file = "ubuntu-zsh_arm64_2022-04-26_00-19-rootfs.tar.zst"
previous_sha256 = "38c3b5bca3a332a75b3a7b1ecab00e24f0a21a52fe8e05d97b17ea8181319f04"

current_version = "latest01"
current_date = "20220427"
old_file = "ubuntu-zsh_arm64_2022-04-19_00-20-rootfs.tar.zst"
old_sha256 = "cfad59ee79ee28969581d9337c5ba5df63ddae40455053bb21180217f9efbf3b"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-zsh_arm64_2022-04-27_13-30-rootfs.tar.zst
# SHA256SUM=052f502307777a7742d03966df288d04d43ae90bfe8c6bc9731cc91cb59d122b
# BUILD_DATE=20220427
# BUILD_TAG=2022-04-27
# STATUS=completed
# VERSION=latest01
# END_TIME=13:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-27
begin = 2022-04-27 13:13:55.310183799+00:00
start-sync_0 = 13:26:03
start-zstd = 13:27:52
start-sync_1 = 13:30:14
end-sync_1 = 13:30:30
end = 2022-04-27 13:30:30.078928178+00:00

[server]
repo = "cake233/ubuntu-zsh-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'
```
