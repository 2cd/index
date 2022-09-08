# alpine-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name alpine-zsh-armv7 \
    cake233/alpine-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it alpine-zsh-armv7 zsh
```

## alpine-zsh-armv7.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2022-09-08"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_armhf_2022-09-08_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b14e1a7e596e2e45e2eb3ce03fe5874c78331365dac4e9c38c9b9d3038b119c4"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "79M"
tar_bytes = 82049024

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "28M"
zstd_bytes = 28430806

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220901"
previous_tag = "2022-09-01"
previous_file = "alpine-zsh_armhf_2022-09-01_00-06-rootfs.tar.zst"
previous_sha256 = "5c86625d8936eb45debf9aa76701de843a07d92d927d53046c186946a440ff29"

current_version = "latest02"
current_date = "20220908"
old_file = "alpine-zsh_armhf_2022-08-25_00-05-rootfs.tar.zst"
old_sha256 = "984351edc1eb6523883874a4db2e9e30d6022e045f5e7bfc33b0ad1f8de29bc7"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-zsh_armhf_2022-09-08_00-05-rootfs.tar.zst
# SHA256SUM=b14e1a7e596e2e45e2eb3ce03fe5874c78331365dac4e9c38c9b9d3038b119c4
# BUILD_DATE=20220908
# BUILD_TAG=2022-09-08
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-08
begin = 2022-09-08 00:02:21.637019368+00:00
start-sync_0 = 00:03:51
start-zstd = 00:05:12
start-sync_1 = 00:05:35
end-sync_1 = 00:05:42
end = 2022-09-08 00:05:42.049957581+00:00

[server]
repo = "cake233/alpine-zsh-armv7"

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
ldd = 'musl libc (armhf) Version 1.2.3'
zsh = 'zsh 5.9 (armv7-alpine-linux-musleabihf)'
```
