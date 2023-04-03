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
tag = ["latest", "2023-04-03"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "jdk_amd64_2023-04-03_12-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f3fdd11a8411755b4af92607f3e253f1094dd01f5523aa2d371ca2a725032bc2"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "438M"
tar_bytes = 458930176

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "187M"
zstd_bytes = 195873702

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230320"
previous_tag = "2023-03-20"
previous_file = "jdk_amd64_2023-03-20_12-08-rootfs.tar.zst"
previous_sha256 = "ff56807b40b28a8ee982ebbc272f1b5a535b76b5e72f480d01079b8ef4c7a8a3"

current_version = "latest01"
current_date = "20230403"
old_file = "jdk_amd64_2023-03-06_12-07-rootfs.tar.zst"
old_sha256 = "c2f9e86e9a98c12dd8288d1eeb2185c3b7d3044263a5f0a7eae0d7c1ce2aa50a"
# edition 2021
# DISTRO_NAME=jdk_amd64
# ROOTFS_FILE=jdk_amd64_2023-04-03_12-07-rootfs.tar.zst
# SHA256SUM=f3fdd11a8411755b4af92607f3e253f1094dd01f5523aa2d371ca2a725032bc2
# BUILD_DATE=20230403
# BUILD_TAG=2023-04-03
# STATUS=completed
# VERSION=latest01
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-03
begin = 2023-04-03 12:02:37.874118683+00:00
start-sync_0 = 12:03:26
start-zstd = 12:03:37
start-sync_1 = 12:07:14
end-sync_1 = 12:07:30
end = 2023-04-03 12:07:30.053829392+00:00

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
PATH = "/usr/local/openjdk-20/bin${PATH:+:${PATH}}"
JAVA_HOME = '/usr/local/openjdk-20'

[version]
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
java = '''
openjdk 20 2023-03-21
OpenJDK Runtime Environment (build 20+36-2344)
OpenJDK 64-Bit Server VM (build 20+36-2344, mixed mode, sharing)
'''
javac = 'javac 20'
```
