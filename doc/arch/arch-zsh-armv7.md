# arch-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-armv7 \
    cake233/arch-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it arch-zsh-armv7 zsh
```

## arch-zsh-armv7.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2022-10-05"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_armhf_2022-10-05_00-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a5df36e5d30db896544dd2d788b41dc093a0233b090a02eb310c854116d34163"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "870M"
tar_bytes = 911897600

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "214M"
zstd_bytes = 223938957

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220928"
previous_tag = "2022-09-28"
previous_file = "arch-zsh_armhf_2022-09-28_00-34-rootfs.tar.zst"
previous_sha256 = "5c0cf8cc3a37e18fba2adced30a7db8dfcfd4970ed562695da4b734a7716ee10"

current_version = "latest01"
current_date = "20221005"
old_file = "arch-zsh_armhf_2022-09-21_00-17-rootfs.tar.zst"
old_sha256 = "b69ae8a284b45a201818deca7be5de234b4840f1a2eba64093f288178ad2ce3b"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-zsh_armhf_2022-10-05_00-29-rootfs.tar.zst
# SHA256SUM=a5df36e5d30db896544dd2d788b41dc093a0233b090a02eb310c854116d34163
# BUILD_DATE=20221005
# BUILD_TAG=2022-10-05
# STATUS=completed
# VERSION=latest01
# END_TIME=00:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-05
begin = 2022-10-05 00:09:24.150992852+00:00
start-sync_0 = 00:24:12
start-zstd = 00:25:43
start-sync_1 = 00:29:18
end-sync_1 = 00:29:38
end = 2022-10-05 00:29:38.757905083+00:00

[server]
repo = "cake233/arch-zsh-armv7"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (armv7l-unknown-linux-gnueabihf)'
```
