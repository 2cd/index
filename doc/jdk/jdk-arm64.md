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
tag = ["latest", "2022-09-19"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "jdk_arm64_2022-09-19_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a3f18d4b90be8188b00893f880e1717c92da089e739d9af7e0c44d15c4e1ca71"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "431M"
tar_bytes = 451319808

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "184M"
zstd_bytes = 192494444

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220905"
previous_tag = "2022-09-05"
previous_file = "jdk_arm64_2022-09-05_12-10-rootfs.tar.zst"
previous_sha256 = "b6de0e14e5faaa467c39d90882f1c6069c3dfff5c9fa44b00e412f419f2f4c3d"

current_version = "latest01"
current_date = "20220919"
old_file = "jdk_arm64_2022-08-22_12-08-rootfs.tar.zst"
old_sha256 = "2fd2148b823ae6d9c8d6a43a780642f1e0d4887172175041b3ad4eaa9e6f1dce"
# edition 2021
# DISTRO_NAME=jdk_arm64
# ROOTFS_FILE=jdk_arm64_2022-09-19_12-09-rootfs.tar.zst
# SHA256SUM=a3f18d4b90be8188b00893f880e1717c92da089e739d9af7e0c44d15c4e1ca71
# BUILD_DATE=20220919
# BUILD_TAG=2022-09-19
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-19
begin = 2022-09-19 12:02:25.540886339+00:00
start-sync_0 = 12:04:59
start-zstd = 12:05:10
start-sync_1 = 12:08:45
end-sync_1 = 12:09:02
end = 2022-09-19 12:09:02.174912090+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u4) 2.31'
java = '''
openjdk 20-ea 2023-03-21
OpenJDK Runtime Environment (build 20-ea+14-949)
OpenJDK 64-Bit Server VM (build 20-ea+14-949, mixed mode, sharing)
'''
javac = 'javac 20-ea'
```
