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
tag = ["latest", "2022-07-11"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "jdk_amd64_2022-07-11_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "13072b7117d3a8da075b574198c253989c843ed3589e77c82cf4460b7d5a0744"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "436M"
tar_bytes = 456488448

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "186M"
zstd_bytes = 194929837

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220627"
previous_tag = "2022-06-27"
previous_file = "jdk_amd64_2022-06-27_12-08-rootfs.tar.zst"
previous_sha256 = "4eb5b77f43bf8518b7df5070d614b93a672d50f38d29cfaa5364614948f04db3"

current_version = "latest01"
current_date = "20220711"
old_file = "jdk_amd64_2022-06-13_12-07-rootfs.tar.zst"
old_sha256 = "6c8c85c7335c8942cf01e8c064216923f69322aff6176cc1ade14a49269bb2b3"
# edition 2021
# DISTRO_NAME=jdk_amd64
# ROOTFS_FILE=jdk_amd64_2022-07-11_12-08-rootfs.tar.zst
# SHA256SUM=13072b7117d3a8da075b574198c253989c843ed3589e77c82cf4460b7d5a0744
# BUILD_DATE=20220711
# BUILD_TAG=2022-07-11
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-11
begin = 2022-07-11 12:02:35.944334295+00:00
start-sync_0 = 12:03:27
start-zstd = 12:03:48
start-sync_1 = 12:07:53
end-sync_1 = 12:08:16
end = 2022-07-11 12:08:16.356383854+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
java = '''
openjdk 20-ea 2023-03-21
OpenJDK Runtime Environment (build 20-ea+4-158)
OpenJDK 64-Bit Server VM (build 20-ea+4-158, mixed mode, sharing)
'''
javac = 'javac 20-ea'
```
