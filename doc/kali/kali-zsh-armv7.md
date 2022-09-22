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
tag = ["zsh", "2022-09-22"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_armhf_2022-09-22_12-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "122784aea30f4049d344ea6f7fb1358b02f6520564926e3a6e562b17475530f8"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "726M"
tar_bytes = 761102336

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "141M"
zstd_bytes = 147704039

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220915"
previous_tag = "2022-09-15"
previous_file = "kali-zsh_armhf_2022-09-15_12-22-rootfs.tar.zst"
previous_sha256 = "0c3baf1367ba40f8fea347ca1457adb10a5f03ffbefb71dfc7cfad92b64fc349"

current_version = "latest01"
current_date = "20220922"
old_file = "kali-zsh_armhf_2022-09-08_12-17-rootfs.tar.zst"
old_sha256 = "eb101534000f43dd83595d848fe2462962c5b2f9eea29c98c1679ef62c3fd80b"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2022-09-22_12-17-rootfs.tar.zst
# SHA256SUM=122784aea30f4049d344ea6f7fb1358b02f6520564926e3a6e562b17475530f8
# BUILD_DATE=20220922
# BUILD_TAG=2022-09-22
# STATUS=completed
# VERSION=latest01
# END_TIME=12:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-22
begin = 2022-09-22 12:02:25.016339549+00:00
start-sync_0 = 12:13:49
start-zstd = 12:15:36
start-sync_1 = 12:17:35
end-sync_1 = 12:17:51
end = 2022-09-22 12:17:51.095830378+00:00

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
ldd = 'ldd (Debian GLIBC 2.34-4) 2.34'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```
