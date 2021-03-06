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
tag = ["latest", "2022-07-11"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "jdk_arm64_2022-07-11_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "654ca9fe9245843a60dd7c7a5b40eef384113358ec5a40ec07c085ebb4f145cc"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "432M"
tar_bytes = 452601856

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "184M"
zstd_bytes = 192629472

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220627"
previous_tag = "2022-06-27"
previous_file = "jdk_arm64_2022-06-27_12-09-rootfs.tar.zst"
previous_sha256 = "8b4e772f08ca5df7b706ee069e60d1caff8fed081884baa8cc9bc972000ed06c"

current_version = "latest01"
current_date = "20220711"
old_file = "jdk_arm64_2022-06-13_12-09-rootfs.tar.zst"
old_sha256 = "e5dd3de21f56a227bc9d5df0eb0a4e20698f481695302fbb9878b72479ba4745"
# edition 2021
# DISTRO_NAME=jdk_arm64
# ROOTFS_FILE=jdk_arm64_2022-07-11_12-09-rootfs.tar.zst
# SHA256SUM=654ca9fe9245843a60dd7c7a5b40eef384113358ec5a40ec07c085ebb4f145cc
# BUILD_DATE=20220711
# BUILD_TAG=2022-07-11
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-11
begin = 2022-07-11 12:02:30.325855181+00:00
start-sync_0 = 12:05:10
start-zstd = 12:05:24
start-sync_1 = 12:09:13
end-sync_1 = 12:09:31
end = 2022-07-11 12:09:31.295764167+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
java = '''
openjdk 20-ea 2023-03-21
OpenJDK Runtime Environment (build 20-ea+4-158)
OpenJDK 64-Bit Server VM (build 20-ea+4-158, mixed mode, sharing)
'''
javac = 'javac 20-ea'
```
