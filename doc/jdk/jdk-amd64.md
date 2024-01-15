# jdk-amd64

## How to run it?

```sh
docker run \
    -it \
    --name jdk-amd64 \
    cake233/jdk-amd64
```

## How to exec shell?

```sh
docker exec -it jdk-amd64 bash
```

## jdk-amd64.toml

```toml
[main]
name = "jdk"
tag = ["latest", "2024-01-15"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "jdk_amd64_2024-01-15_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1124525258d0f92974eac4f42d53bf1b136bab71bd5dacf98bf8e9b6bd685114"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "452M"
tar_bytes = 473057792

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "193M"
zstd_bytes = 202094083

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20240115"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=jdk_amd64
# ROOTFS_FILE=jdk_amd64_2024-01-15_12-08-rootfs.tar.zst
# SHA256SUM=1124525258d0f92974eac4f42d53bf1b136bab71bd5dacf98bf8e9b6bd685114
# BUILD_DATE=20240115
# BUILD_TAG=2024-01-15
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-15
begin = 2024-01-15 12:02:36.965775145+00:00
start-sync_0 = 12:04:05
start-zstd = 12:04:20
start-sync_1 = 12:07:44
end-sync_1 = 12:08:01
end = 2024-01-15 12:08:01.181859832+00:00

[server]
repo = "cake233/jdk-amd64"

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
PATH = "/usr/local/openjdk-21/bin${PATH:+:${PATH}}"
JAVA_HOME = '/usr/local/openjdk-21'

[version]
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u3) 2.36'
java = '''
openjdk 21 2023-09-19
OpenJDK Runtime Environment (build 21+35-2513)
OpenJDK 64-Bit Server VM (build 21+35-2513, mixed mode, sharing)
'''
javac = 'javac 21'
```
