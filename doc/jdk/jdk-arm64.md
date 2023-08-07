# jdk-arm64

## How to run it?

```sh
docker run \
    -it \
    --name jdk-arm64 \
    cake233/jdk-arm64
```

## How to exec shell?

```sh
docker exec -it jdk-arm64 bash
```

## jdk-arm64.toml

```toml
[main]
name = "jdk"
tag = ["latest", "2023-08-07"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "jdk_arm64_2023-08-07_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d4070d0d6ab5ec7a85ca7c8b07484c92c180527f4002df3d27a53b22ce25c025"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "433M"
tar_bytes = 453474304

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "185M"
zstd_bytes = 193280301

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230724"
previous_tag = "2023-07-24"
previous_file = "jdk_arm64_2023-07-24_12-09-rootfs.tar.zst"
previous_sha256 = "a91b3e3c8ad25ab98518448efc740216060fcad0ffc2790a2dd29d7b21e20e6e"

current_version = "latest01"
current_date = "20230807"
old_file = "jdk_arm64_2023-07-10_12-10-rootfs.tar.zst"
old_sha256 = "3c4083c9dccaf2854702ce30ef36471ccaa8701bd50b8e9ba440af9b9bbdeaf2"
# edition 2021
# DISTRO_NAME=jdk_arm64
# ROOTFS_FILE=jdk_arm64_2023-08-07_12-10-rootfs.tar.zst
# SHA256SUM=d4070d0d6ab5ec7a85ca7c8b07484c92c180527f4002df3d27a53b22ce25c025
# BUILD_DATE=20230807
# BUILD_TAG=2023-08-07
# STATUS=completed
# VERSION=latest01
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-07
begin = 2023-08-07 12:02:41.184295585+00:00
start-sync_0 = 12:06:00
start-zstd = 12:06:13
start-sync_1 = 12:09:49
end-sync_1 = 12:10:12
end = 2023-08-07 12:10:12.344412154+00:00

[server]
repo = "cake233/jdk-arm64"

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
PATH = "/usr/local/openjdk-20/bin${PATH:+:${PATH}}"
JAVA_HOME = '/usr/local/openjdk-20'

[version]
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u6) 2.31'
java = '''
openjdk 20 2023-03-21
OpenJDK Runtime Environment (build 20+36-2344)
OpenJDK 64-Bit Server VM (build 20+36-2344, mixed mode, sharing)
'''
javac = 'javac 20'
```
