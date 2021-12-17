# rust-armv7

## How to run it?

```shell
docker run \
    -it \
    --name rust-armv7 \
    cake233/rust-armv7
```

## How to exec shell?

```shell
    docker exec -it rust-armv7 bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/rs-project:/app \
    -w /app \
    cake233/rust-armv7 \
    cargo b --release
```

## rust-armv7.toml

```toml
[main]
name = "rust"
tag = ["latest", "2021-12-17", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "rust_armhf_2021-12-17_00-15.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "de6d72729232a588d7b99814360096391c04b6fe58b133f705fdc92c0e6da192"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "926M"
tar_bytes = 970844672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "227M"
zstd_bytes = 237126156

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211213"
previous_tag = "2021-12-13"
previous_file = "rust_armhf_2021-12-13_00-12-rootfs.tar.zst"
previous_sha256 = "1d6275e9c43eeeccb03038f59435e37ac8bebda494c404bb454da2023be73396"

current_version = "latest02"
current_date = "20211217"
old_file = "rust_armhf_2021-12-10_00-14-rootfs.tar.zst"
old_sha256 = "204bc5bcc3f03f3361ef29626a308c4e2827aa8f725f1ebf1f4c608565da8d70"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2021-12-17_00-15-rootfs.tar.zst
# SHA256SUM=de6d72729232a588d7b99814360096391c04b6fe58b133f705fdc92c0e6da192
# BUILD_DATE=20211217
# BUILD_TAG=2021-12-17
# STATUS=completed
# VERSION=latest02
# END_TIME=00:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-17
begin = 2021-12-17 00:02:29.866360054+00:00
start-sync_0 = 00:09:48
start-zstd = 00:10:39
start-sync_1 = 00:14:41
end-sync_1 = 00:15:02
end = 2021-12-17 00:15:02.555983052+00:00

[server]
repo = "cake233/rust-armv7"

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
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'ldd (Debian GLIBC 2.33-1) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.59.0-nightly (a359ce160 2021-12-14)'
rustc = 'rustc 1.59.0-nightly (c5ecc1570 2021-12-15)'
cc = 'cc (Debian 11.2.0-12) 11.2.0'
cargo_verbose = '''
cargo 1.59.0-nightly (a359ce160 2021-12-14)
release: 1.59.0-nightly
commit-hash: a359ce16073401f28b84840da85b268aa3d37c88
commit-date: 2021-12-14
host: armv7-unknown-linux-gnueabihf
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.59.0-nightly (c5ecc1570 2021-12-15)
binary: rustc
commit-hash: c5ecc157043ba413568b09292001a4a74b541a4e
commit-date: 2021-12-15
host: armv7-unknown-linux-gnueabihf
release: 1.59.0-nightly
LLVM version: 13.0.0
'''
```
