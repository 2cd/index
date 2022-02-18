# manjaro-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name manjaro-zsh-amd64 \
    cake233/manjaro-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it manjaro-zsh-amd64 zsh
```

## manjaro-zsh-amd64.toml

```toml
[main]
name = "manjaro"
tag = ["zsh", "2022-02-18"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "manjaro-zsh_amd64_2022-02-18_12-12.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "44509673dc3dc8eb89af5a87801fc6717216722c3f0622e5ac5c70436dbb2878"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1172025856

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "258M"
zstd_bytes = 269562591

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220211"
previous_tag = "2022-02-11"
previous_file = "manjaro-zsh_amd64_2022-02-11_12-11-rootfs.tar.zst"
previous_sha256 = "9ec53f3ebc59e40bebd585532ec7fae0c3fe426e752cae31d11c03b2736a4906"

current_version = "latest01"
current_date = "20220218"
old_file = "manjaro-zsh_amd64_2022-02-04_12-12-rootfs.tar.zst"
old_sha256 = "511d64fd633e38fee1080baffe7a973824470b4b09ea2c33fdf99676fea24ba2"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2022-02-18_12-12-rootfs.tar.zst
# SHA256SUM=44509673dc3dc8eb89af5a87801fc6717216722c3f0622e5ac5c70436dbb2878
# BUILD_DATE=20220218
# BUILD_TAG=2022-02-18
# STATUS=completed
# VERSION=latest01
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-18
begin = 2022-02-18 12:02:27.074482281+00:00
start-sync_0 = 12:05:12
start-zstd = 12:06:45
start-sync_1 = 12:11:40
end-sync_1 = 12:12:03
end = 2022-02-18 12:12:03.550933771+00:00

[server]
repo = "cake233/manjaro-zsh-amd64"

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
ldd = 'ldd (GNU libc) 2.33'
zsh = 'zsh 5.8 (x86_64-pc-linux-gnu)'
```
