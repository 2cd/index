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
tag = ["latest", "2022-10-03"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "jdk_amd64_2022-10-03_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5820fbc09bf24b79f4505b11aa1caa68044c0be6499415e9bc5e30835c4a7c24"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "436M"
tar_bytes = 456845312

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "187M"
zstd_bytes = 195061527

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220919"
previous_tag = "2022-09-19"
previous_file = "jdk_amd64_2022-09-19_12-08-rootfs.tar.zst"
previous_sha256 = "ee679d5833ed94032fad8fb435a6f3b733d796b98451a7e0a9d5bb00bad902c3"

current_version = "latest02"
current_date = "20221003"
old_file = "jdk_amd64_2022-09-05_12-08-rootfs.tar.zst"
old_sha256 = "4cabb338aa6b65d01c3e503c4a566ff2c6ec38bdb8e67be32aa498568e2de3c7"
# edition 2021
# DISTRO_NAME=jdk_amd64
# ROOTFS_FILE=jdk_amd64_2022-10-03_12-08-rootfs.tar.zst
# SHA256SUM=5820fbc09bf24b79f4505b11aa1caa68044c0be6499415e9bc5e30835c4a7c24
# BUILD_DATE=20221003
# BUILD_TAG=2022-10-03
# STATUS=completed
# VERSION=latest02
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-03
begin = 2022-10-03 12:02:27.567832512+00:00
start-sync_0 = 12:03:42
start-zstd = 12:03:57
start-sync_1 = 12:08:01
end-sync_1 = 12:08:20
end = 2022-10-03 12:08:20.697915078+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u4) 2.31'
java = '''
openjdk 20-ea 2023-03-21
OpenJDK Runtime Environment (build 20-ea+17-1181)
OpenJDK 64-Bit Server VM (build 20-ea+17-1181, mixed mode, sharing)
'''
javac = 'javac 20-ea'
```
