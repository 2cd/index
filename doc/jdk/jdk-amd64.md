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
tag = ["latest", "2023-11-13"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "jdk_amd64_2023-11-13_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b5923a2040aa359e5dff42bd7511a258c287d0e7689993d6324884bfbe0190a0"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "452M"
tar_bytes = 473044992

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "193M"
zstd_bytes = 202114828

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231016"
previous_tag = "2023-10-16"
previous_file = "jdk_amd64_2023-10-16_12-08-rootfs.tar.zst"
previous_sha256 = "617bce0c184138685e9ce6a8bf8fdde0780834ccfb6ae3bd3cec669846d96e09"

current_version = "latest01"
current_date = "20231113"
old_file = "jdk_amd64_2023-10-02_12-08-rootfs.tar.zst"
old_sha256 = "9a6e4b78008a3020a0bb154207577701bca8136dda7c48f67acb77f30c78480b"
# edition 2021
# DISTRO_NAME=jdk_amd64
# ROOTFS_FILE=jdk_amd64_2023-11-13_12-10-rootfs.tar.zst
# SHA256SUM=b5923a2040aa359e5dff42bd7511a258c287d0e7689993d6324884bfbe0190a0
# BUILD_DATE=20231113
# BUILD_TAG=2023-11-13
# STATUS=completed
# VERSION=latest01
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-13
begin = 2023-11-13 12:02:37.365348278+00:00
start-sync_0 = 12:04:34
start-zstd = 12:04:51
start-sync_1 = 12:09:43
end-sync_1 = 12:10:07
end = 2023-11-13 12:10:07.684582500+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u3) 2.36'
java = '''
openjdk 21 2023-09-19
OpenJDK Runtime Environment (build 21+35-2513)
OpenJDK 64-Bit Server VM (build 21+35-2513, mixed mode, sharing)
'''
javac = 'javac 21'
```
