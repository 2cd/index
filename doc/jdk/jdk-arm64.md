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
tag = ["latest", "2024-01-15"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "jdk_arm64_2024-01-15_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "057fa34a900645d5f1b957a58c7bc9330b1f2823600aebcc62b9300f3e45a8c0"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "476M"
tar_bytes = 498486272

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "190M"
zstd_bytes = 199103534

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
# DISTRO_NAME=jdk_arm64
# ROOTFS_FILE=jdk_arm64_2024-01-15_12-09-rootfs.tar.zst
# SHA256SUM=057fa34a900645d5f1b957a58c7bc9330b1f2823600aebcc62b9300f3e45a8c0
# BUILD_DATE=20240115
# BUILD_TAG=2024-01-15
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-15
begin = 2024-01-15 12:02:34.912320252+00:00
start-sync_0 = 12:05:49
start-zstd = 12:06:03
start-sync_1 = 12:09:11
end-sync_1 = 12:09:27
end = 2024-01-15 12:09:27.679851534+00:00

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
