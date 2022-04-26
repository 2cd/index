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
tag = ["base", "2022-04-26"]
os = "euler"
release = "base"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "euler_arm64_2022-04-26_02-43.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "251e60bda16c89d24cd07cd1b48b111e9887b91a829926f2aaf73a94c6b0eabd"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "475M"
tar_bytes = 497821184

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "68M"
zstd_bytes = 70302233

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220422"
previous_tag = "2022-04-22"
previous_file = "euler_arm64_2022-04-22_00-51-rootfs.tar.zst"
previous_sha256 = "3b229d82a7c24481bb77a99aa6c0a5118047233698ad3144e8da652a348a572f"

current_version = "latest02"
current_date = "20220426"
old_file = "euler_arm64_2022-04-22_09-53-rootfs.tar.zst"
old_sha256 = "bb127dfdc951680c8e70fe6ab16e167061f7b01d65afb2ce3b67ed99197f6d42"
# edition 2021
# DISTRO_NAME=euler_arm64
# ROOTFS_FILE=euler_arm64_2022-04-26_02-43-rootfs.tar.zst
# SHA256SUM=251e60bda16c89d24cd07cd1b48b111e9887b91a829926f2aaf73a94c6b0eabd
# BUILD_DATE=20220426
# BUILD_TAG=2022-04-26
# STATUS=completed
# VERSION=latest02
# END_TIME=02:43

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-26
begin = 2022-04-26 02:37:54.251776596+00:00
start-sync_0 = 02:41:10
start-zstd = 02:41:32
start-sync_1 = 02:42:52
end-sync_1 = 02:43:05
end = 2022-04-26 02:43:05.197366818+00:00

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
