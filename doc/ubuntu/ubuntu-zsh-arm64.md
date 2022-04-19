# ubuntu-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-zsh-arm64 \
    cake233/ubuntu-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it ubuntu-zsh-arm64 zsh
```

## ubuntu-zsh-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2022-04-19", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "ubuntu-zsh_arm64_2022-04-19_00-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "cfad59ee79ee28969581d9337c5ba5df63ddae40455053bb21180217f9efbf3b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "622M"
tar_bytes = 651781632

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "112M"
zstd_bytes = 117292299

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220411"
previous_tag = "2022-04-11"
previous_file = "ubuntu-zsh_arm64_2022-04-11_23-16-rootfs.tar.zst"
previous_sha256 = "681a41a23cbf5fd6ae896fcdb2b03118ddafd3081ac48814c0bfba5c6a26c57d"

current_version = "latest01"
current_date = "20220419"
old_file = "ubuntu-zsh_arm64_2022-04-04_23-21-rootfs.tar.zst"
old_sha256 = "b45bebcd0ef31ea6c8859d36840c47f20517df6c661dff688777f805969e901b"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-zsh_arm64_2022-04-19_00-20-rootfs.tar.zst
# SHA256SUM=cfad59ee79ee28969581d9337c5ba5df63ddae40455053bb21180217f9efbf3b
# BUILD_DATE=20220419
# BUILD_TAG=2022-04-19
# STATUS=completed
# VERSION=latest01
# END_TIME=00:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-19
begin = 2022-04-19 00:02:23.669375528+00:00
start-sync_0 = 00:16:04
start-zstd = 00:17:50
start-sync_1 = 00:20:23
end-sync_1 = 00:20:34
end = 2022-04-19 00:20:34.992985788+00:00

[server]
repo = "cake233/ubuntu-zsh-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'
```
