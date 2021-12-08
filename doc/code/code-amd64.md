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
tag = ["latest", "2021-12-08", "vsc", "vscode", "web"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "code_amd64_2021-12-08_01-10.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "2232ddbfec5d2d40648e2f8b03eb385dba5643b0b986755b02f591df0874661a"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "520M"
tar_bytes = 544236032

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "106M"
zstd_bytes = 110759683

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211128"
previous_tag = "2021-11-28"
previous_file = "code_amd64_2021-11-28_23-01-rootfs.tar.zst"
previous_sha256 = ""

current_version = "latest02"
current_date = "20211208"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=code_amd64
# ROOTFS_FILE=code_amd64_2021-12-08_01-10-rootfs.tar.zst
# SHA256SUM=2232ddbfec5d2d40648e2f8b03eb385dba5643b0b986755b02f591df0874661a
# BUILD_DATE=20211208
# BUILD_TAG=2021-12-08
# STATUS=completed
# VERSION=latest02
# END_TIME=01:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-08
begin = 2021-12-08 01:06:14.622728930+00:00
start-sync_0 = 01:07:45
start-zstd = 01:08:26
start-sync_1 = 01:10:27
end-sync_1 = 01:10:45
end = 2021-12-08 01:10:45.503828414+00:00

[server]
repo = "cake233/code-amd64"

[server.node1]
name = "cn"
current = false
previous = true
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
code = '3.12.0 b37ff28a0a582aee84a8f961755d0cb40a4081db'

[port]
tcp = [8080]
```
