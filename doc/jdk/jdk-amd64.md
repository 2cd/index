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
tag = ["latest", "2023-05-15"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "jdk_amd64_2023-05-15_12-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e3262c640d4e94a79d534244f14282182e35a2885c07212530feb890cb69d804"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "438M"
tar_bytes = 458966016

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "187M"
zstd_bytes = 196001737

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230501"
previous_tag = "2023-05-01"
previous_file = "jdk_amd64_2023-05-01_12-07-rootfs.tar.zst"
previous_sha256 = "bc9b42a7a5fdad59825e216ed7d55a8fb1556b70d42fcb8694c3b628aed038da"

current_version = "latest02"
current_date = "20230515"
old_file = "jdk_amd64_2023-04-17_12-07-rootfs.tar.zst"
old_sha256 = "bc62e1eff61ef3bac25254dbdc3bca347e11e7904adc8c935a191c218e1e2cf7"
# edition 2021
# DISTRO_NAME=jdk_amd64
# ROOTFS_FILE=jdk_amd64_2023-05-15_12-07-rootfs.tar.zst
# SHA256SUM=e3262c640d4e94a79d534244f14282182e35a2885c07212530feb890cb69d804
# BUILD_DATE=20230515
# BUILD_TAG=2023-05-15
# STATUS=completed
# VERSION=latest02
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-15
begin = 2023-05-15 12:02:39.804608807+00:00
start-sync_0 = 12:03:42
start-zstd = 12:03:56
start-sync_1 = 12:07:36
end-sync_1 = 12:07:52
end = 2023-05-15 12:07:52.394852778+00:00

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
