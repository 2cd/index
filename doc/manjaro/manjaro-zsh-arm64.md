# manjaro-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name manjaro-zsh-arm64 \
    cake233/manjaro-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it manjaro-zsh-arm64 zsh
```

## manjaro-zsh-arm64.toml

```toml
[main]
name = "manjaro"
tag = ["zsh", "2022-09-02"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_arm64_2022-09-02_12-21.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "04b0aff79c1b712100f32a7d9feb05859601de3689b1208361f6bf00b9222235"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1074092544

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "236M"
zstd_bytes = 247374150

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220826"
previous_tag = "2022-08-26"
previous_file = "manjaro-zsh_arm64_2022-08-26_12-21-rootfs.tar.zst"
previous_sha256 = "3fbddf9031f283e8fedd148084e1741f1b5516c14000d54a9d9e6326bf400f25"

current_version = "latest01"
current_date = "20220902"
old_file = "manjaro-zsh_arm64_2022-08-19_12-23-rootfs.tar.zst"
old_sha256 = "84acc36e5e94fef8baa846ca3bfa398538a95245a353fdc1432fd69eb6420e47"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2022-09-02_12-21-rootfs.tar.zst
# SHA256SUM=04b0aff79c1b712100f32a7d9feb05859601de3689b1208361f6bf00b9222235
# BUILD_DATE=20220902
# BUILD_TAG=2022-09-02
# STATUS=completed
# VERSION=latest01
# END_TIME=12:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-02
begin = 2022-09-02 12:02:20.756462967+00:00
start-sync_0 = 12:15:27
start-zstd = 12:17:07
start-sync_1 = 12:20:48
end-sync_1 = 12:21:07
end = 2022-09-02 12:21:07.321396112+00:00

[server]
repo = "cake233/manjaro-zsh-arm64"

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
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
