# kali-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-armv7 \
    cake233/kali-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it kali-zsh-armv7 zsh
```

## kali-zsh-armv7.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2022-07-14"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_armhf_2022-07-14_12-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c946a908dd7adb8afe2a4d6a5c33b6b1fe968dd07e6a289554ca1b63096ec8ee"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "684M"
tar_bytes = 716532736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "142M"
zstd_bytes = 148506926

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220707"
previous_tag = "2022-07-07"
previous_file = "kali-zsh_armhf_2022-07-07_12-17-rootfs.tar.zst"
previous_sha256 = "464e9133fef1dab7c9447a1fc2fd2034af3abd09366d85e6c68c3a036fea0973"

current_version = "latest01"
current_date = "20220714"
old_file = "kali-zsh_armhf_2022-06-30_12-20-rootfs.tar.zst"
old_sha256 = "065fcaf57840f1927a270820d417ee764ecbb8d781197ee27e9ddc1266f4a3ad"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2022-07-14_12-16-rootfs.tar.zst
# SHA256SUM=c946a908dd7adb8afe2a4d6a5c33b6b1fe968dd07e6a289554ca1b63096ec8ee
# BUILD_DATE=20220714
# BUILD_TAG=2022-07-14
# STATUS=completed
# VERSION=latest01
# END_TIME=12:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-14
begin = 2022-07-14 12:02:29.779396242+00:00
start-sync_0 = 12:12:55
start-zstd = 12:14:37
start-sync_1 = 12:16:41
end-sync_1 = 12:16:54
end = 2022-07-14 12:16:54.694879000+00:00

[server]
repo = "cake233/kali-zsh-armv7"

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```
