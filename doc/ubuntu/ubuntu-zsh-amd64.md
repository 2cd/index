# ubuntu-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-zsh-amd64 \
    cake233/ubuntu-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it ubuntu-zsh-amd64 zsh
```

## ubuntu-zsh-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2022-05-03", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_amd64_2022-05-03_00-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9ddaa803f852d583beef8ce2295e3b64f0c28f6c56a83934111ddf51a3ea0c28"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "635M"
tar_bytes = 665376768

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "114M"
zstd_bytes = 118833053

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220427"
previous_tag = "2022-04-27"
previous_file = "ubuntu-zsh_amd64_2022-04-27_13-19-rootfs.tar.zst"
previous_sha256 = "dd2b559b128c42741544ad6365204a2d6dbffaba9cd054db71fb0f6df6409d27"

current_version = "latest02"
current_date = "20220503"
old_file = "ubuntu-zsh_amd64_2022-04-26_00-08-rootfs.tar.zst"
old_sha256 = "bbcc27661e6ef884243164eb87dfb201aa2655021f8104d3a1019a7e6f8b66c8"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-zsh_amd64_2022-05-03_00-09-rootfs.tar.zst
# SHA256SUM=9ddaa803f852d583beef8ce2295e3b64f0c28f6c56a83934111ddf51a3ea0c28
# BUILD_DATE=20220503
# BUILD_TAG=2022-05-03
# STATUS=completed
# VERSION=latest02
# END_TIME=00:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-03
begin = 2022-05-03 00:02:33.723785232+00:00
start-sync_0 = 00:04:27
start-zstd = 00:06:14
start-sync_1 = 00:08:45
end-sync_1 = 00:09:01
end = 2022-05-03 00:09:01.979638954+00:00

[server]
repo = "cake233/ubuntu-zsh-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.8.1 (x86_64-ubuntu-linux-gnu)'
```
