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
tag = ["latest", "2022-04-18"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "jdk_amd64_2022-04-18_12-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "eea1a9d8add4ddf9cdfb6679f5fed4e5a954e1286e58a8b8b794c8d9a27e1db7"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "431M"
tar_bytes = 450930688

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "184M"
zstd_bytes = 192726302

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220404"
previous_tag = "2022-04-04"
previous_file = "jdk_amd64_2022-04-04_11-07-rootfs.tar.zst"
previous_sha256 = "0e7126954cb6162d12b7139277d6caa9fef7cdb2d7efc77c85ca1c0907255da5"

current_version = "latest01"
current_date = "20220418"
old_file = "jdk_amd64_2022-03-21_12-08-rootfs.tar.zst"
old_sha256 = "dde49b30525d06a8465da2b18b8a4f400727dceb9ef0b31869fdd4def3b9106a"
# edition 2021
# DISTRO_NAME=jdk_amd64
# ROOTFS_FILE=jdk_amd64_2022-04-18_12-07-rootfs.tar.zst
# SHA256SUM=eea1a9d8add4ddf9cdfb6679f5fed4e5a954e1286e58a8b8b794c8d9a27e1db7
# BUILD_DATE=20220418
# BUILD_TAG=2022-04-18
# STATUS=completed
# VERSION=latest01
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-18
begin = 2022-04-18 12:02:30.027318925+00:00
start-sync_0 = 12:03:37
start-zstd = 12:03:48
start-sync_1 = 12:07:33
end-sync_1 = 12:07:48
end = 2022-04-18 12:07:48.823085282+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
previous = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
PATH = "/usr/local/openjdk-19/bin${PATH:+:${PATH}}"
JAVA_HOME = '/usr/local/openjdk-19'

[version]
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
java = '''
openjdk 19-ea 2022-09-20
OpenJDK Runtime Environment (build 19-ea+17-1142)
OpenJDK 64-Bit Server VM (build 19-ea+17-1142, mixed mode, sharing)
'''
javac = 'javac 19-ea'
```
