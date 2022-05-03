# ubuntu-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-zsh-armv7 \
    cake233/ubuntu-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it ubuntu-zsh-armv7 zsh
```

## ubuntu-zsh-armv7.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2022-05-03", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_armhf_2022-05-03_00-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b92e6dc599a848c1d119bb4bbe6c65cf932881b0e8de0124b7f080b3a41bf9ae"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "575M"
tar_bytes = 602697216

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "109M"
zstd_bytes = 113578953

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220427"
previous_tag = "2022-04-27"
previous_file = "ubuntu-zsh_armhf_2022-04-27_13-34-rootfs.tar.zst"
previous_sha256 = "6523fdd2d39b24a4ad4639771d252e4616c9e7aeaf10e4e325faf2126b343d44"

current_version = "latest02"
current_date = "20220503"
old_file = "ubuntu-zsh_armhf_2022-04-26_00-20-rootfs.tar.zst"
old_sha256 = "38e2ef48efd905e7df0cf3929d41fc89679636c9c211f013ad449e42235c9c5a"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-zsh_armhf_2022-05-03_00-17-rootfs.tar.zst
# SHA256SUM=b92e6dc599a848c1d119bb4bbe6c65cf932881b0e8de0124b7f080b3a41bf9ae
# BUILD_DATE=20220503
# BUILD_TAG=2022-05-03
# STATUS=completed
# VERSION=latest02
# END_TIME=00:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-03
begin = 2022-05-03 00:02:31.337809377+00:00
start-sync_0 = 00:13:55
start-zstd = 00:15:36
start-sync_1 = 00:17:44
end-sync_1 = 00:17:56
end = 2022-05-03 00:17:56.197217473+00:00

[server]
repo = "cake233/ubuntu-zsh-armv7"

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
zsh = 'zsh 5.8.1 (arm-unknown-linux-gnueabihf)'
```
