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
tag = ["latest", "2023-05-29"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "jdk_arm64_2023-05-29_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b7d5bbd34ce8c29510f47fb92b054f79ae671319796bf728147f2a8b481280de"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "433M"
tar_bytes = 453479424

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "185M"
zstd_bytes = 193351860

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230515"
previous_tag = "2023-05-15"
previous_file = "jdk_arm64_2023-05-15_12-10-rootfs.tar.zst"
previous_sha256 = "59bb828fb5100768bfce67c4d20e840ff07aabe93d3b59ac1b2ee2dd5609ac3e"

current_version = "latest01"
current_date = "20230529"
old_file = "jdk_arm64_2023-05-01_12-11-rootfs.tar.zst"
old_sha256 = "cfe83a7ec08db571323b37312ae4c321c83ceb9342b7e316507a3f60ade8254b"
# edition 2021
# DISTRO_NAME=jdk_arm64
# ROOTFS_FILE=jdk_arm64_2023-05-29_12-09-rootfs.tar.zst
# SHA256SUM=b7d5bbd34ce8c29510f47fb92b054f79ae671319796bf728147f2a8b481280de
# BUILD_DATE=20230529
# BUILD_TAG=2023-05-29
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-29
begin = 2023-05-29 12:02:41.106050762+00:00
start-sync_0 = 12:05:25
start-zstd = 12:05:37
start-sync_1 = 12:09:08
end-sync_1 = 12:09:23
end = 2023-05-29 12:09:23.494214887+00:00

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
