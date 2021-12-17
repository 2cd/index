# rust-mips64le

## How to run it?

```shell
docker run \
    -it \
    --name rust-mips64le \
    cake233/rust-mips64le
```

## How to exec shell?

```shell
    docker exec -it rust-mips64le bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/rs-project:/app \
    -w /app \
    cake233/rust-mips64le \
    cargo b --release
```

## rust-mips64le.toml

```toml
[main]
name = "rust"
tag = ["latest", "2021-12-17", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
x11_or_wayland = false

[file]
name = "rust_mips64el_2021-12-17_00-15.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "1f04c19d8a6b09d807a9ea31e98e2c190e393c492705b20cb8a752b5e4596821"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1017M"
tar_bytes = 1066115584

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "202M"
zstd_bytes = 211039956

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211213"
previous_tag = "2021-12-13"
previous_file = "rust_mips64el_2021-12-13_00-13-rootfs.tar.zst"
previous_sha256 = "15621f14f0089de26ec1a05ff7ea06eb7810b2a1d20fa7654693ca527adef77a"

current_version = "latest02"
current_date = "20211217"
old_file = "rust_mips64el_2021-12-10_00-15-rootfs.tar.zst"
old_sha256 = "917ae8a6ab360123c830f41584c598602c8c2b72e610e834b56886bc8bb6c249"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2021-12-17_00-15-rootfs.tar.zst
# SHA256SUM=1f04c19d8a6b09d807a9ea31e98e2c190e393c492705b20cb8a752b5e4596821
# BUILD_DATE=20211217
# BUILD_TAG=2021-12-17
# STATUS=completed
# VERSION=latest02
# END_TIME=00:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-17
begin = 2021-12-17 00:02:26.467334625+00:00
start-sync_0 = 00:09:14
start-zstd = 00:10:02
start-sync_1 = 00:14:42
end-sync_1 = 00:15:04
end = 2021-12-17 00:15:04.197846515+00:00

[server]
repo = "cake233/rust-mips64le"

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
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.59.0-nightly (c5ecc1570 2021-12-15)
binary: rustc
commit-hash: c5ecc157043ba413568b09292001a4a74b541a4e
commit-date: 2021-12-15
host: mips64el-unknown-linux-gnuabi64
release: 1.59.0-nightly
LLVM version: 13.0.0
'''
```
