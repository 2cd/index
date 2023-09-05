# debian-zsh-386

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-386 \
    cake233/debian-zsh-386
```

## How to exec shell?

```sh
docker exec -it debian-zsh-386 zsh
```

## debian-zsh-386.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2023-08-30"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_i386_2023-08-30_12-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "42901bb43fab749aa3c778d90ba7c9729cf39e7bab871d8bb85c219e6b39d040"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "821M"
tar_bytes = 860182528

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "167M"
zstd_bytes = 174124087

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230830"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-zsh_i386_2023-08-30_12-20-rootfs.tar.zst
# SHA256SUM=42901bb43fab749aa3c778d90ba7c9729cf39e7bab871d8bb85c219e6b39d040
# BUILD_DATE=20230830
# BUILD_TAG=2023-08-30
# STATUS=completed
# VERSION=latest01
# END_TIME=12:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-30
begin = 2023-08-30 12:02:43.010332708+00:00
start-sync_0 = 12:15:06
start-zstd = 12:16:54
start-sync_1 = 12:20:07
end-sync_1 = 12:20:32
end = 2023-08-30 12:20:32.163377927+00:00

[server]
repo = "cake233/debian-zsh-386"

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

[version]
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'
```