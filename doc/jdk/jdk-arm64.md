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
tag = ["latest", "2023-01-09"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "jdk_arm64_2023-01-09_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "787d441aa4a0671092e2e8429d7fa5a9d19f57e1887b956cba66376064f3116e"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "433M"
tar_bytes = 453381632

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "185M"
zstd_bytes = 193274161

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221226"
previous_tag = "2022-12-26"
previous_file = "jdk_arm64_2022-12-26_12-08-rootfs.tar.zst"
previous_sha256 = "5677923199ded2501fc76f54487d3fd201085d5e18567c45f5e70c0834be61cf"

current_version = "latest01"
current_date = "20230109"
old_file = "jdk_arm64_2022-12-12_12-09-rootfs.tar.zst"
old_sha256 = "d33974d559faad224fa0fac9fbfc946e4a4ee6f506848cf3c8d1f4b3b071fa8b"
# edition 2021
# DISTRO_NAME=jdk_arm64
# ROOTFS_FILE=jdk_arm64_2023-01-09_12-08-rootfs.tar.zst
# SHA256SUM=787d441aa4a0671092e2e8429d7fa5a9d19f57e1887b956cba66376064f3116e
# BUILD_DATE=20230109
# BUILD_TAG=2023-01-09
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-09
begin = 2023-01-09 12:02:30.243237139+00:00
start-sync_0 = 12:04:43
start-zstd = 12:04:54
start-sync_1 = 12:08:15
end-sync_1 = 12:08:30
end = 2023-01-09 12:08:30.264059842+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
java = '''
openjdk 20-ea 2023-03-21
OpenJDK Runtime Environment (build 20-ea+30-2297)
OpenJDK 64-Bit Server VM (build 20-ea+30-2297, mixed mode, sharing)
'''
javac = 'javac 20-ea'
```
