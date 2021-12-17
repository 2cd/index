# rust-s390x

## How to run it?

```shell
docker run \
    -it \
    --name rust-s390x \
    cake233/rust-s390x
```

## How to exec shell?

```shell
    docker exec -it rust-s390x bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/rs-project:/app \
    -w /app \
    cake233/rust-s390x \
    cargo b --release
```

## rust-s390x.toml

```toml
[main]
name = "rust"
tag = ["latest", "2021-12-17", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
x11_or_wayland = false

[file]
name = "rust_s390x_2021-12-17_00-16.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "a81b8d074aa7c12b60924b9ed7721f7c3e214eea68cb5fbb0735b7c9c147ea80"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1081244160

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "216M"
zstd_bytes = 225575756

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211213"
previous_tag = "2021-12-13"
previous_file = "rust_s390x_2021-12-13_00-13-rootfs.tar.zst"
previous_sha256 = "1213d9a0ddf339959177bace41cc622432facaff01eb18f769cd74a22de8889a"

current_version = "latest02"
current_date = "20211217"
old_file = "rust_s390x_2021-12-10_00-15-rootfs.tar.zst"
old_sha256 = "50d6159a177af82ed17e565d91ca37a0c191b0da6317e3d0e4b3a979fccd7ad3"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2021-12-17_00-16-rootfs.tar.zst
# SHA256SUM=a81b8d074aa7c12b60924b9ed7721f7c3e214eea68cb5fbb0735b7c9c147ea80
# BUILD_DATE=20211217
# BUILD_TAG=2021-12-17
# STATUS=completed
# VERSION=latest02
# END_TIME=00:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-17
begin = 2021-12-17 00:02:30.376639536+00:00
start-sync_0 = 00:09:57
start-zstd = 00:10:58
start-sync_1 = 00:15:43
end-sync_1 = 00:16:08
end = 2021-12-17 00:16:08.272722333+00:00

[server]
repo = "cake233/rust-s390x"

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
host: s390x-unknown-linux-gnu
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.59.0-nightly (c5ecc1570 2021-12-15)
binary: rustc
commit-hash: c5ecc157043ba413568b09292001a4a74b541a4e
commit-date: 2021-12-15
host: s390x-unknown-linux-gnu
release: 1.59.0-nightly
LLVM version: 13.0.0
'''
```
