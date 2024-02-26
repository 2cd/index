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
tag = ["latest", "2024-02-26"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "jdk_amd64_2024-02-26_12-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "10f6c1a80a6ae55b94d4c828551c4cee617b3ab75455e12486bed1fcb6fa1972"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "452M"
tar_bytes = 473062912

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "193M"
zstd_bytes = 202114363

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231127"
previous_tag = "2023-11-27"
previous_file = "jdk_amd64_2023-11-27_12-08-rootfs.tar.zst"
previous_sha256 = "261055552eca8f7bc7cd6839d3b8492cbe6378ad5e442109a65cc55152ab31c0"

current_version = "latest01"
current_date = "20240226"
old_file = "jdk_amd64_2023-11-13_12-10-rootfs.tar.zst"
old_sha256 = "b5923a2040aa359e5dff42bd7511a258c287d0e7689993d6324884bfbe0190a0"
# edition 2021
# DISTRO_NAME=jdk_amd64
# ROOTFS_FILE=jdk_amd64_2024-02-26_12-07-rootfs.tar.zst
# SHA256SUM=10f6c1a80a6ae55b94d4c828551c4cee617b3ab75455e12486bed1fcb6fa1972
# BUILD_DATE=20240226
# BUILD_TAG=2024-02-26
# STATUS=completed
# VERSION=latest01
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-26
begin = 2024-02-26 12:02:33.676110094+00:00
start-sync_0 = 12:03:50
start-zstd = 12:03:59
start-sync_1 = 12:07:16
end-sync_1 = 12:07:28
end = 2024-02-26 12:07:28.934030525+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u4) 2.36'
java = '''
openjdk 21 2023-09-19
OpenJDK Runtime Environment (build 21+35-2513)
OpenJDK 64-Bit Server VM (build 21+35-2513, mixed mode, sharing)
'''
javac = 'javac 21'
```
