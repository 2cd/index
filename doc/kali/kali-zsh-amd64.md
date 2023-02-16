# kali-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-amd64 \
    cake233/kali-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it kali-zsh-amd64 zsh
```

## kali-zsh-amd64.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2023-02-16"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_amd64_2023-02-16_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "299f240cd1cad3fc4490506d22f229cd4aa3d5302240b99153dd0a4a8e6ce881"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "773M"
tar_bytes = 810378752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "150M"
zstd_bytes = 156957984

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230209"
previous_tag = "2023-02-09"
previous_file = "kali-zsh_amd64_2023-02-09_12-09-rootfs.tar.zst"
previous_sha256 = "0179480a3865ceececae15c26dccfe961b13b67ef6f1d611b9d5061ecedbf7dc"

current_version = "latest02"
current_date = "20230216"
old_file = "kali-zsh_amd64_2023-02-02_12-10-rootfs.tar.zst"
old_sha256 = "2933c661033d9a0546a2da5fece4f845ce88ba48cc48a679690a29fdbafa4680"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2023-02-16_12-09-rootfs.tar.zst
# SHA256SUM=299f240cd1cad3fc4490506d22f229cd4aa3d5302240b99153dd0a4a8e6ce881
# BUILD_DATE=20230216
# BUILD_TAG=2023-02-16
# STATUS=completed
# VERSION=latest02
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-16
begin = 2023-02-16 12:02:26.981585764+00:00
start-sync_0 = 12:04:47
start-zstd = 12:06:38
start-sync_1 = 12:09:22
end-sync_1 = 12:09:39
end = 2023-02-16 12:09:39.318973076+00:00

[server]
repo = "cake233/kali-zsh-amd64"

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
