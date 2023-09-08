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
tag = ["zsh", "2023-09-08"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_amd64_2023-09-08_12-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5a9c3a51d8ede839fd7c8de80427dc61db19a6c2f135526a9897a3b05a9303ab"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1275770368

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "293M"
zstd_bytes = 306409586

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230901"
previous_tag = "2023-09-01"
previous_file = "manjaro-zsh_amd64_2023-09-01_12-12-rootfs.tar.zst"
previous_sha256 = "89f9c0db163a49eab783cfcbe0c38f63c75b508d3b6814acd387e7a52bdb0956"

current_version = "latest02"
current_date = "20230908"
old_file = "manjaro-zsh_amd64_2023-08-25_12-14-rootfs.tar.zst"
old_sha256 = "a052b78a38a4942a3c86edf603d11693f68eaab3d42f6c24be6f07435b6f26e6"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2023-09-08_12-13-rootfs.tar.zst
# SHA256SUM=5a9c3a51d8ede839fd7c8de80427dc61db19a6c2f135526a9897a3b05a9303ab
# BUILD_DATE=20230908
# BUILD_TAG=2023-09-08
# STATUS=completed
# VERSION=latest02
# END_TIME=12:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-08
begin = 2023-09-08 12:02:35.354934669+00:00
start-sync_0 = 12:06:26
start-zstd = 12:08:15
start-sync_1 = 12:12:57
end-sync_1 = 12:13:31
end = 2023-09-08 12:13:31.971274117+00:00

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

[version]
ldd = 'ldd (GNU libc) 2.38'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
