# euler-amd64

## How to run it?

```sh
docker run \
    -it \
    --name euler-amd64 \
    cake233/euler-amd64
```

## How to exec shell?

```sh
docker exec -it euler-amd64 sh
```

## euler-amd64.toml

```toml
[main]
name = "euler"
tag = ["base", "2022-04-22"]
os = "euler"
release = "base"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "euler_amd64_2022-04-22_00-34.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "cb652b74328d608a352bf22b28a112ba03b290644b4bd812b9f8918327e36c13"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "216M"
tar_bytes = 226017792

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "51M"
zstd_bytes = 52433930

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220422"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=euler_amd64
# ROOTFS_FILE=euler_amd64_2022-04-22_00-34-rootfs.tar.zst
# SHA256SUM=cb652b74328d608a352bf22b28a112ba03b290644b4bd812b9f8918327e36c13
# BUILD_DATE=20220422
# BUILD_TAG=2022-04-22
# STATUS=completed
# VERSION=latest01
# END_TIME=00:34

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-22
begin = 2022-04-22 00:32:21.076133670+00:00
start-sync_0 = 00:33:27
start-zstd = 00:33:41
start-sync_1 = 00:34:24
end-sync_1 = 00:34:36
end = 2022-04-22 00:34:36.192905544+00:00

[server]
repo = "cake233/euler-amd64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = false
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
previous = false
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
