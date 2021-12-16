# code-amd64

## How to run it?

```shell
docker run \
    -it \
    --name code-amd64 \
    cake233/code-amd64
```

## How to exec shell?

```shell
    docker exec -it code-amd64 bash
```

## code-amd64.toml

```toml
[main]
name = "code"
tag = ["latest", "2021-12-16", "vsc", "vscode", "web"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "code_amd64_2021-12-16_08-23.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "2e64d00edd980abc03f0deb69fd0125392eaa121607237789ebd3085ac0c9382"

# zstd: [1-22]
zstd-level = 11

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "757M"
tar_bytes = 793269248

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "204M"
zstd_bytes = 213827559

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211208"
previous_tag = "2021-12-08"
previous_file = "code_amd64_2021-12-08_01-10-rootfs.tar.zst"
previous_sha256 = "2232ddbfec5d2d40648e2f8b03eb385dba5643b0b986755b02f591df0874661a"

current_version = "latest01"
current_date = "20211216"
old_file = "code_amd64_2021-11-28_23-01-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=code_amd64
# ROOTFS_FILE=code_amd64_2021-12-16_08-23-rootfs.tar.zst
# SHA256SUM=2e64d00edd980abc03f0deb69fd0125392eaa121607237789ebd3085ac0c9382
# BUILD_DATE=20211216
# BUILD_TAG=2021-12-16
# STATUS=completed
# VERSION=latest01
# END_TIME=08:23

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-16
begin = 2021-12-16 08:20:40.691637224+00:00
start-sync_0 = 08:21:39
start-zstd = 08:22:25
start-sync_1 = 08:22:37
end-sync_1 = 08:23:00
end = 2021-12-16 08:23:00.765645581+00:00

[server]
repo = "cake233/code-amd64"

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
