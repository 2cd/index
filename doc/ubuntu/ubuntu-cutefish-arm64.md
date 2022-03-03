# ubuntu-cutefish-arm64

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-cutefish-arm64 \
    cake233/ubuntu-cutefish-arm64
```

## How to exec shell?

```sh
docker exec -it ubuntu-cutefish-arm64 sh
```

## ubuntu-cutefish-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["cutefish", "2022-03-03", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "ubuntu-cutefish_arm64_2022-03-03_06-51.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "ac4853eaa8541fad8e6f5fe96d498edf5fb1fd5acee26ffc2dc76983079330d9"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "160M"
tar_bytes = 167211008

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "112M"
zstd_bytes = 117377680

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220303"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-cutefish_arm64_2022-03-03_06-51-rootfs.tar.zst
# SHA256SUM=ac4853eaa8541fad8e6f5fe96d498edf5fb1fd5acee26ffc2dc76983079330d9
# BUILD_DATE=20220303
# BUILD_TAG=2022-03-03
# STATUS=completed
# VERSION=latest01
# END_TIME=06:51

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-03
begin = 2022-03-03 01:56:31.863170358+00:00
start-sync_0 = 06:50:12
start-zstd = 06:51:16
start-sync_1 = 06:51:21
end-sync_1 = 06:51:37
end = 2022-03-03 06:51:37.543476456+00:00

[server]
repo = "cake233/ubuntu-cutefish-arm64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
previous = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
