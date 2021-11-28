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
tag = ["latest", "2021-11-28", "vsc", "vscode", "web"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "code_amd64_2021-11-28_22-33.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "9eda3254d573bda7ea867ff8bc67cd29205ee11d0c418815ff294650618e3e97"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "520M"
tar_bytes = 544225792

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "106M"
zstd_bytes = 110758601

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211128"
last_tag = ""
last_file = ""

current_version = "latest01"
current_date = "20211128"
# edition 2021
# DISTRO_NAME=code_amd64
# ROOTFS_FILE=code_amd64_2021-11-28_22-33.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest01
# END_TIME=22:33

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 22:30:20.938063652+00:00
start-sync_0 = 22:31:08
start-zstd = 22:31:42
start-sync_1 = 22:33:37
end-sync_1 = 22:33:51
end = 2021-11-28 22:33:51.651879790+00:00

[server]
repo = "cake233/code-amd64"

[server.node1]
name = "cn"
current = false
last = true
split = false

[server.node2]
name = "us"
current = false
last = true
split = false
part = 12

[server.node3]
name = "global"
current = false
last = true
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
