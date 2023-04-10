# node-arm64

## How to run it?

```sh
docker run \
    -it \
    --name node-arm64 \
    cake233/node-arm64
```

## How to exec shell?

```sh
docker exec -it node-arm64 bash
```

## node-arm64.toml

```toml
[main]
name = "node"
tag = ["latest", "2023-04-10"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "node_arm64_2023-04-10_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ef6d7d8963ef1c6dc64dbedc0c587192a89959e5d90ddff0537dfa6be0042ae5"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "953M"
tar_bytes = 998327296

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "198M"
zstd_bytes = 207446707

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230327"
previous_tag = "2023-03-27"
previous_file = "node_arm64_2023-03-27_12-13-rootfs.tar.zst"
previous_sha256 = "f67ac50bfee464f2610aa814bf2777a4bdcfc3a7127b3cae75976b037588350f"

current_version = "latest01"
current_date = "20230410"
old_file = "node_arm64_2023-03-13_12-13-rootfs.tar.zst"
old_sha256 = "e667461400729b4a3054c67d0192e904bebf4968fa0354db862b4052c79aa013"
# edition 2021
# DISTRO_NAME=node_arm64
# ROOTFS_FILE=node_arm64_2023-04-10_12-11-rootfs.tar.zst
# SHA256SUM=ef6d7d8963ef1c6dc64dbedc0c587192a89959e5d90ddff0537dfa6be0042ae5
# BUILD_DATE=20230410
# BUILD_TAG=2023-04-10
# STATUS=completed
# VERSION=latest01
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-10
begin = 2023-04-10 12:02:34.007933736+00:00
start-sync_0 = 12:05:56
start-zstd = 12:06:13
start-sync_1 = 12:10:53
end-sync_1 = 12:11:11
end = 2023-04-10 12:11:11.503532204+00:00

[server]
repo = "cake233/node-arm64"

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
node = 'v19.8.1'
yarn = '1.22.19'
npm = '9.5.1'
```
