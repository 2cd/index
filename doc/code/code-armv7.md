# code-armv7

## How to run it?

```sh
docker run \
    -it \
    --name code-armv7 \
    cake233/code-armv7
```

## How to exec shell?

```sh
docker exec -it code-armv7 bash
```

## code-armv7.toml

```toml
[main]
name = "code"
tag = ["latest", "2021-12-27", "vsc", "vscode", "web"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "code_armhf_2021-12-27_12-12.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "17a79b4bee04cfbf229c0052575d2351abaac503da000cc0988ec2cc62d69dd6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "618M"
tar_bytes = 647196160

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "154M"
zstd_bytes = 160627901

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211216"
previous_tag = "2021-12-16"
previous_file = "code_armhf_2021-12-16_08-49-rootfs.tar.zst"
previous_sha256 = "d340c2941b846bd5a41f8c672dc618ac6840626f1c78acdbc9581a7a3354ddb4"

current_version = "latest02"
current_date = "20211227"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=code_armhf
# ROOTFS_FILE=code_armhf_2021-12-27_12-12-rootfs.tar.zst
# SHA256SUM=17a79b4bee04cfbf229c0052575d2351abaac503da000cc0988ec2cc62d69dd6
# BUILD_DATE=20211227
# BUILD_TAG=2021-12-27
# STATUS=completed
# VERSION=latest02
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-27
begin = 2021-12-27 12:02:28.428286025+00:00
start-sync_0 = 12:08:47
start-zstd = 12:09:35
start-sync_1 = 12:12:03
end-sync_1 = 12:12:23
end = 2021-12-27 12:12:23.783597614+00:00

[server]
repo = "cake233/code-armv7"

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

[version]
ldd = 'ldd (Debian GLIBC 2.33-1) 2.33'
code = '4.0.0 0f395955515207f9b461ffdd2a595f35311dd05f'

[port]
tcp = [8080]
```
