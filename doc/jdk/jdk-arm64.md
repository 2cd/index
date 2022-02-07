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
tag = ["latest", "2022-02-07"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "jdk_arm64_2022-02-07_12-07.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "e3ed9e8614a5154a1ae95b3576d99000ff0bb9f0d3bd00b380615128d8b12b07"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "419M"
tar_bytes = 438387712

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "181M"
zstd_bytes = 189314514

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220124"
previous_tag = "2022-01-24"
previous_file = "jdk_arm64_2022-01-24_12-07-rootfs.tar.zst"
previous_sha256 = "ecad6dbfe2f0f37a8ec147bb0b10704db47bb22e5d75d9785c99838d0ef5beff"

current_version = "latest02"
current_date = "20220207"
old_file = "jdk_arm64_2022-01-10_12-08-rootfs.tar.zst"
old_sha256 = "094db98712a75cea1ed3921e3e7053424277a956bc00a87f3c071cf382da301f"
# edition 2021
# DISTRO_NAME=jdk_arm64
# ROOTFS_FILE=jdk_arm64_2022-02-07_12-07-rootfs.tar.zst
# SHA256SUM=e3ed9e8614a5154a1ae95b3576d99000ff0bb9f0d3bd00b380615128d8b12b07
# BUILD_DATE=20220207
# BUILD_TAG=2022-02-07
# STATUS=completed
# VERSION=latest02
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-07
begin = 2022-02-07 12:02:32.110481522+00:00
start-sync_0 = 12:04:42
start-zstd = 12:04:58
start-sync_1 = 12:06:45
end-sync_1 = 12:07:04
end = 2022-02-07 12:07:04.530513520+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u2) 2.31'
java = '''
openjdk 19-ea 2022-09-20
OpenJDK Runtime Environment (build 19-ea+7-366)
OpenJDK 64-Bit Server VM (build 19-ea+7-366, mixed mode, sharing)
'''
javac = 'javac 19-ea'
```
