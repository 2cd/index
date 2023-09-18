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
tag = ["latest", "2023-09-18"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "jdk_arm64_2023-09-18_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a15f85ae9242d934db910204291b3a99abd315c0f1c869ee2d04b57c12964e5b"

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
zstd_bytes = 193284479

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230904"
previous_tag = "2023-09-04"
previous_file = "jdk_arm64_2023-09-04_12-10-rootfs.tar.zst"
previous_sha256 = "14c4ef0d89786ae1a79cb220b08bc2bd918d4f7653293f582bcfec41bcc80587"

current_version = "latest02"
current_date = "20230918"
old_file = "jdk_arm64_2023-08-21_12-12-rootfs.tar.zst"
old_sha256 = "772daf1c0cccaa958ca60295d1c0cb233ae3174876c46357fa7042b3365ad5bd"
# edition 2021
# DISTRO_NAME=jdk_arm64
# ROOTFS_FILE=jdk_arm64_2023-09-18_12-09-rootfs.tar.zst
# SHA256SUM=a15f85ae9242d934db910204291b3a99abd315c0f1c869ee2d04b57c12964e5b
# BUILD_DATE=20230918
# BUILD_TAG=2023-09-18
# STATUS=completed
# VERSION=latest02
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-18
begin = 2023-09-18 12:02:39.446953740+00:00
start-sync_0 = 12:05:36
start-zstd = 12:05:47
start-sync_1 = 12:09:30
end-sync_1 = 12:09:52
end = 2023-09-18 12:09:52.831470541+00:00

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
