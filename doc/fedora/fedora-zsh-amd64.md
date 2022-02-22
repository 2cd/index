# fedora-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name fedora-zsh-amd64 \
    cake233/fedora-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it fedora-zsh-amd64 zsh
```

## fedora-zsh-amd64.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2022-02-22"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "fedora-zsh_amd64_2022-02-22_12-10.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "9c6c6623a1b46efa1d23b1687160b84dbb09fad4f378d5bc9e28f65009c90dc3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "964M"
tar_bytes = 1009819648

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "165M"
zstd_bytes = 172570106

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220215"
previous_tag = "2022-02-15"
previous_file = "fedora-zsh_amd64_2022-02-15_12-11-rootfs.tar.zst"
previous_sha256 = "50eeea8b82fb847d49257de4a2710e112fc9e26b8e6071c757f4a9e4e7c348cc"

current_version = "latest02"
current_date = "20220222"
old_file = "fedora-zsh_amd64_2022-02-08_12-10-rootfs.tar.zst"
old_sha256 = "f21f756858e319582fd7cee228fed3fa6631ffcb275a81e3242e37ce5b41573f"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2022-02-22_12-10-rootfs.tar.zst
# SHA256SUM=9c6c6623a1b46efa1d23b1687160b84dbb09fad4f378d5bc9e28f65009c90dc3
# BUILD_DATE=20220222
# BUILD_TAG=2022-02-22
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-22
begin = 2022-02-22 12:02:31.334452333+00:00
start-sync_0 = 12:04:36
start-zstd = 12:06:40
start-sync_1 = 12:10:15
end-sync_1 = 12:10:31
end = 2022-02-22 12:10:31.121948025+00:00

[server]
repo = "cake233/fedora-zsh-amd64"

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

[version]
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.8.1 (x86_64-redhat-linux-gnu)'
```
