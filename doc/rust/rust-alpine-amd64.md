# rust-alpine-amd64

## How to run it?

```shell
docker run \
    -it \
    --name rust-alpine-amd64 \
    cake233/rust-alpine-amd64
```

## How to exec shell?

```shell
    docker exec -it rust-alpine-amd64 bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/rs-project:/app \
    -w /app \
    cake233/rust-alpine-amd64 \
    cargo b --release
```

## rust-alpine-amd64.toml

```toml
[main]
name = "rust"
tag = ["alpine", "2021-12-17", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "rust-musl_amd64_2021-12-17_00-07.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "c83f6252f6fc19f4ae860299cf178d33924964adb2d5464bbf1195541a84bf69"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "833M"
tar_bytes = 873123328

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "190M"
zstd_bytes = 198724972

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211213"
previous_tag = "2021-12-13"
previous_file = "rust-musl_amd64_2021-12-13_00-06-rootfs.tar.zst"
previous_sha256 = "afe20d3be5eea3b090371f90638f065f43070c7e6c2f2c2fa575c5d81dbb83bf"

current_version = "latest02"
current_date = "20211217"
old_file = "rust-musl_amd64_2021-12-10_00-07-rootfs.tar.zst"
old_sha256 = "19b2e39f53177ed38c7fa169cbacee744edef0dabc5deb68ab420e426f727863"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2021-12-17_00-07-rootfs.tar.zst
# SHA256SUM=c83f6252f6fc19f4ae860299cf178d33924964adb2d5464bbf1195541a84bf69
# BUILD_DATE=20211217
# BUILD_TAG=2021-12-17
# STATUS=completed
# VERSION=latest02
# END_TIME=00:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-17
begin = 2021-12-17 00:02:29.224021105+00:00
start-sync_0 = 00:03:22
start-zstd = 00:04:16
start-sync_1 = 00:07:11
end-sync_1 = 00:07:30
end = 2021-12-17 00:07:31.015456757+00:00

[server]
repo = "cake233/rust-alpine-amd64"

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
LANG = "C.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'musl libc (x86_64) Version 1.2.2'
rustup = 'rustup 1.24.3 (2021-05-31)'
cargo = 'cargo 1.59.0-nightly (a359ce160 2021-12-14)'
rustc = 'rustc 1.59.0-nightly (c5ecc1570 2021-12-15)'
cc = 'cc (Alpine 11.2.1_git20211128) 11.2.1 20211128'
cargo_verbose = '''
cargo 1.59.0-nightly (a359ce160 2021-12-14)
release: 1.59.0-nightly
commit-hash: a359ce16073401f28b84840da85b268aa3d37c88
commit-date: 2021-12-14
host: x86_64-unknown-linux-musl
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Alpine Linux 3.15.0_alpha20210804 [64-bit]
'''
rustc_verbose = '''
rustc 1.59.0-nightly (c5ecc1570 2021-12-15)
binary: rustc
commit-hash: c5ecc157043ba413568b09292001a4a74b541a4e
commit-date: 2021-12-15
host: x86_64-unknown-linux-musl
release: 1.59.0-nightly
LLVM version: 13.0.0
'''
```
