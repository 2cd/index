# kali-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-amd64 \
    cake233/kali-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it kali-zsh-amd64 zsh
```

## kali-zsh-amd64.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2023-08-10"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2023-08-10_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "302edfbadca1be4d43d7e726ef8530d548fc545a5976e4a34a298e6983af4cbb"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "777M"
tar_bytes = 814230528

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "151M"
zstd_bytes = 158130263

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230803"
previous_tag = "2023-08-03"
previous_file = "kali-zsh_amd64_2023-08-03_12-09-rootfs.tar.zst"
previous_sha256 = "baf473ca698c9cb492532b939892930b74ad6673fc382eae0d1ffba7aa071299"

current_version = "latest02"
current_date = "20230810"
old_file = "kali-zsh_amd64_2023-07-27_12-10-rootfs.tar.zst"
old_sha256 = "660a417f916b81718f02be5d396caba51fa6f72a8d42e280d3d8648f3e095a9b"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2023-08-10_12-09-rootfs.tar.zst
# SHA256SUM=302edfbadca1be4d43d7e726ef8530d548fc545a5976e4a34a298e6983af4cbb
# BUILD_DATE=20230810
# BUILD_TAG=2023-08-10
# STATUS=completed
# VERSION=latest02
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-10
begin = 2023-08-10 12:02:31.755887221+00:00
start-sync_0 = 12:04:49
start-zstd = 12:06:38
start-sync_1 = 12:09:27
end-sync_1 = 12:09:45
end = 2023-08-10 12:09:45.713696600+00:00

[server]
repo = "cake233/kali-zsh-amd64"

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
ldd = 'ldd (Debian GLIBC 2.37-6) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
