# rust-ppc64le

## How to run it?

```shell
docker run \
    -it \
    --name rust-ppc64le \
    cake233/rust-ppc64le
```

## How to exec shell?

```shell
    docker exec -it rust-ppc64le bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/rs-project:/app \
    -w /app \
    cake233/rust-ppc64le \
    cargo b --release
```

## rust-ppc64le.toml

```toml
[main]
name = "rust"
tag = ["latest", "2021-12-17", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
x11_or_wayland = false

[file]
name = "rust_ppc64el_2021-12-17_00-13.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "f7b1fe2b6e27ad54aaed3aba9186b199ffc164e53234fad71e769168c9366433"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1126462464

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "224M"
zstd_bytes = 234331420

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211213"
previous_tag = "2021-12-13"
previous_file = "rust_ppc64el_2021-12-13_00-13-rootfs.tar.zst"
previous_sha256 = "cecfbbaf01045bf0ae1fafb8dd6f5da5470f7c32e482f8c4e70eb16487676f5a"

current_version = "latest02"
current_date = "20211217"
old_file = "rust_ppc64el_2021-12-10_00-14-rootfs.tar.zst"
old_sha256 = "7ea60ed65dee1f67c2c7385a91d039b3dcc948cbbc050d57a41cf662b1e7dc7a"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2021-12-17_00-13-rootfs.tar.zst
# SHA256SUM=f7b1fe2b6e27ad54aaed3aba9186b199ffc164e53234fad71e769168c9366433
# BUILD_DATE=20211217
# BUILD_TAG=2021-12-17
# STATUS=completed
# VERSION=latest02
# END_TIME=00:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-17
begin = 2021-12-17 00:02:25.742652305+00:00
start-sync_0 = 00:08:17
start-zstd = 00:09:00
start-sync_1 = 00:12:53
end-sync_1 = 00:13:13
end = 2021-12-17 00:13:13.617917268+00:00

[server]
repo = "cake233/rust-ppc64le"

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
cc = 'cc (Debian 11.2.0-13) 11.2.0'
cargo_verbose = '''
cargo 1.59.0-nightly (a359ce160 2021-12-14)
release: 1.59.0-nightly
commit-hash: a359ce16073401f28b84840da85b268aa3d37c88
commit-date: 2021-12-14
host: powerpc64le-unknown-linux-gnu
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.59.0-nightly (c5ecc1570 2021-12-15)
binary: rustc
commit-hash: c5ecc157043ba413568b09292001a4a74b541a4e
commit-date: 2021-12-15
host: powerpc64le-unknown-linux-gnu
release: 1.59.0-nightly
LLVM version: 13.0.0
'''
```
