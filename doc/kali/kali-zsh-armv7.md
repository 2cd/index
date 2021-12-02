# kali-zsh-armv7

## How to run it?

```shell
docker run \
    -it \
    --name kali-zsh-armv7 \
    cake233/kali-zsh-armv7
```

## How to exec shell?

```shell
    docker exec -it kali-zsh-armv7 zsh
```

## kali-zsh-armv7.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2021-12-02"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "kali-zsh_armhf_2021-12-02_12-16.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "5f3724f5968288d7581d7acf118b454ec81e025f0def8b15216ae40382f0c7e5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "659M"
tar_bytes = 690935296

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "135M"
zstd_bytes = 141152716

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211202"
last_tag = "2021-12-02"
last_file = "kali-zsh_armhf_2021-12-02_07-36-rootfs.tar.zst"

current_version = "latest01"
current_date = "20211202"
old_file = "kali-zsh_armhf_2021-11-30_15-11-rootfs.tar.zst"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2021-12-02_12-16-rootfs.tar.zst
# BUILD_DATE=20211202
# BUILD_TAG=2021-12-02
# STATUS=completed
# VERSION=latest01
# END_TIME=12:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-02
begin = 2021-12-02 12:01:51.097907809+00:00
start-sync_0 = 12:12:29
start-zstd = 12:14:13
start-sync_1 = 12:16:26
end-sync_1 = 12:16:43
end = 2021-12-02 12:16:43.763185931+00:00

[server]
repo = "cake233/kali-zsh-armv7"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "us"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "global"
current = false
last = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
