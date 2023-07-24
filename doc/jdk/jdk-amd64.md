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
tag = ["latest", "2023-07-24"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "jdk_amd64_2023-07-24_12-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9939189eb2bf99390cb4b9d2e9b628f96508a4b2120bf8569014b59518212568"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "438M"
tar_bytes = 458964992

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "187M"
zstd_bytes = 195986168

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230710"
previous_tag = "2023-07-10"
previous_file = "jdk_amd64_2023-07-10_12-09-rootfs.tar.zst"
previous_sha256 = "757205a42ce31d3b439c4b79517a311e53b44048b1cc1ebd10de085b3980e033"

current_version = "latest02"
current_date = "20230724"
old_file = "jdk_amd64_2023-06-26_12-07-rootfs.tar.zst"
old_sha256 = "34ff08da715b3886ee809f7390baa2fb3084f0f0e143a5625e6e70fe4e48bc2a"
# edition 2021
# DISTRO_NAME=jdk_amd64
# ROOTFS_FILE=jdk_amd64_2023-07-24_12-07-rootfs.tar.zst
# SHA256SUM=9939189eb2bf99390cb4b9d2e9b628f96508a4b2120bf8569014b59518212568
# BUILD_DATE=20230724
# BUILD_TAG=2023-07-24
# STATUS=completed
# VERSION=latest02
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-24
begin = 2023-07-24 12:02:33.035580357+00:00
start-sync_0 = 12:03:27
start-zstd = 12:03:40
start-sync_1 = 12:07:19
end-sync_1 = 12:07:35
end = 2023-07-24 12:07:35.076101812+00:00

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
