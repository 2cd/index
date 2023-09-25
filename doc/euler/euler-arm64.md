# euler-arm64

## How to run it?

```sh
docker run \
    -it \
    --name euler-arm64 \
    cake233/euler-arm64
```

## How to exec shell?

```sh
docker exec -it euler-arm64 sh
```

## euler-arm64.toml

```toml
[main]
name = "euler"
tag = ["base", "2023-03-15"]
os = "euler"
release = "base"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "euler_arm64_2023-03-15_00-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7ef39966b9e270f525fbaffe204565a7c36f7fa5cd3281965c2fe80b7057d67d"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "472M"
tar_bytes = 494872576

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "68M"
zstd_bytes = 70624651

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230215"
previous_tag = "2023-02-15"
previous_file = "euler_arm64_2023-02-15_00-07-rootfs.tar.zst"
previous_sha256 = "af4590b9835dfcea09b00765942b3b941c39dcf0de973ffc791c80ce00c83927"

current_version = "latest01"
current_date = "20230315"
old_file = "euler_arm64_2023-01-15_00-08-rootfs.tar.zst"
old_sha256 = "27ad342f300d7653829f8f742b6075b74ba9718096b1f433146300e2cb96150a"
# edition 2021
# DISTRO_NAME=euler_arm64
# ROOTFS_FILE=euler_arm64_2023-03-15_00-08-rootfs.tar.zst
# SHA256SUM=7ef39966b9e270f525fbaffe204565a7c36f7fa5cd3281965c2fe80b7057d67d
# BUILD_DATE=20230315
# BUILD_TAG=2023-03-15
# STATUS=completed
# VERSION=latest01
# END_TIME=00:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-15
begin = 2023-03-15 00:03:15.727827114+00:00
start-sync_0 = 00:06:30
start-zstd = 00:06:51
start-sync_1 = 00:08:04
end-sync_1 = 00:08:13
end = 2023-03-15 00:08:13.615471935+00:00

[server]
repo = "cake233/euler-arm64"

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
```