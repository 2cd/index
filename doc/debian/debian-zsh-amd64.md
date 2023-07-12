# debian-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-amd64 \
    cake233/debian-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it debian-zsh-amd64 zsh
```

## debian-zsh-amd64.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2023-07-12"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_amd64_2023-07-12_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "dd11a950b46083d720ae170cf98e7aa550add28b680cc77b11997b785e4124cc"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "775M"
tar_bytes = 811985408

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "151M"
zstd_bytes = 157467096

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230705"
previous_tag = "2023-07-05"
previous_file = "debian-zsh_amd64_2023-07-05_12-09-rootfs.tar.zst"
previous_sha256 = "e5da5d9484403b212998699c3bebcb0f0c3b07bdc8e9cda3a9ea7393537f2bdb"

current_version = "latest01"
current_date = "20230712"
old_file = "debian-zsh_amd64_2023-06-28_12-10-rootfs.tar.zst"
old_sha256 = "dd774043eb79b231b8d18b60d496ba9e60b53788cf384f18a8d5882900e17022"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-zsh_amd64_2023-07-12_12-08-rootfs.tar.zst
# SHA256SUM=dd11a950b46083d720ae170cf98e7aa550add28b680cc77b11997b785e4124cc
# BUILD_DATE=20230712
# BUILD_TAG=2023-07-12
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-12
begin = 2023-07-12 12:02:36.207549727+00:00
start-sync_0 = 12:04:15
start-zstd = 12:06:00
start-sync_1 = 12:08:44
end-sync_1 = 12:08:57
end = 2023-07-12 12:08:57.779949255+00:00

[server]
repo = "cake233/debian-zsh-amd64"

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
ldd = 'ldd (Debian GLIBC 2.37-5) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
