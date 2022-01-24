# code-amd64

## How to run it?

```sh
docker run \
    -it \
    --name code-amd64 \
    cake233/code-amd64
```

## How to exec shell?

```sh
docker exec -it code-amd64 bash
```

## code-amd64.toml

```toml
[main]
name = "code"
tag = ["latest", "2022-01-24", "vsc", "vscode", "web"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "code_amd64_2022-01-24_12-07.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "2f64cf3b43625c74eee7ce64002cd54ceb315481783821db75b1dd5af4027f9e"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "757M"
tar_bytes = 793509376

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "172M"
zstd_bytes = 180286122

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220124"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=code_amd64
# ROOTFS_FILE=code_amd64_2022-01-24_12-07-rootfs.tar.zst
# SHA256SUM=2f64cf3b43625c74eee7ce64002cd54ceb315481783821db75b1dd5af4027f9e
# BUILD_DATE=20220124
# BUILD_TAG=2022-01-24
# STATUS=completed
# VERSION=latest01
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-24
begin = 2022-01-24 12:02:24.278565385+00:00
start-sync_0 = 12:03:43
start-zstd = 12:04:27
start-sync_1 = 12:07:39
end-sync_1 = 12:07:59
end = 2022-01-24 12:07:59.860748772+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-3) 2.33'
code = '4.0.1 735c6da829535969ff7193c79379299e4a1cb9bc'

[port]
tcp = [8080]
```
