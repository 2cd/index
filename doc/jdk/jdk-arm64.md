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
tag = ["latest", "2023-02-06"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "jdk_arm64_2023-02-06_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4385f1c9cfe13954c9392c8509d62ac97533f563e4fb8434d15c4f92167b1dc0"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "433M"
tar_bytes = 453413376

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "185M"
zstd_bytes = 193363975

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230123"
previous_tag = "2023-01-23"
previous_file = "jdk_arm64_2023-01-23_12-08-rootfs.tar.zst"
previous_sha256 = "672ac38444ee98d0aed55dced228025276f8312a2c997c8f1032c8710cbf7816"

current_version = "latest01"
current_date = "20230206"
old_file = "jdk_arm64_2023-01-09_12-08-rootfs.tar.zst"
old_sha256 = "787d441aa4a0671092e2e8429d7fa5a9d19f57e1887b956cba66376064f3116e"
# edition 2021
# DISTRO_NAME=jdk_arm64
# ROOTFS_FILE=jdk_arm64_2023-02-06_12-08-rootfs.tar.zst
# SHA256SUM=4385f1c9cfe13954c9392c8509d62ac97533f563e4fb8434d15c4f92167b1dc0
# BUILD_DATE=20230206
# BUILD_TAG=2023-02-06
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-06
begin = 2023-02-06 12:02:33.588144193+00:00
start-sync_0 = 12:04:50
start-zstd = 12:05:06
start-sync_1 = 12:08:09
end-sync_1 = 12:08:29
end = 2023-02-06 12:08:29.116662552+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
java = '''
openjdk 20-ea 2023-03-21
OpenJDK Runtime Environment (build 20-ea+34-2340)
OpenJDK 64-Bit Server VM (build 20-ea+34-2340, mixed mode, sharing)
'''
javac = 'javac 20-ea'
```
