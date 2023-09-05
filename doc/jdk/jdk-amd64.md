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
tag = ["latest", "2023-09-04"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "jdk_amd64_2023-09-04_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a2e2faaeac20254e7b747bed754e5654b54d76d1209a60fbdca7f1e697cfecd6"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "438M"
tar_bytes = 458964992

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "187M"
zstd_bytes = 195987113

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230904"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=jdk_amd64
# ROOTFS_FILE=jdk_amd64_2023-09-04_12-08-rootfs.tar.zst
# SHA256SUM=a2e2faaeac20254e7b747bed754e5654b54d76d1209a60fbdca7f1e697cfecd6
# BUILD_DATE=20230904
# BUILD_TAG=2023-09-04
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-04
begin = 2023-09-04 12:02:51.803737902+00:00
start-sync_0 = 12:04:22
start-zstd = 12:04:35
start-sync_1 = 12:08:17
end-sync_1 = 12:08:37
end = 2023-09-04 12:08:37.745194249+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u6) 2.31'
java = '''
openjdk 20 2023-03-21
OpenJDK Runtime Environment (build 20+36-2344)
OpenJDK 64-Bit Server VM (build 20+36-2344, mixed mode, sharing)
'''
javac = 'javac 20'
```