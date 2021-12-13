# rust-arm64

## How to run it?

```shell
docker run \
    -it \
    --name rust-arm64 \
    cake233/rust-arm64
```

## How to exec shell?

```shell
    docker exec -it rust-arm64 bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/rs-project:/app \
    -w /app \
    cake233/rust-arm64 \
    cargo b --release
```

## rust-arm64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2021-12-13", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "rust_arm64_2021-12-13_00-15.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "f5a493e2f9e997323c823c590ca289b716df7d9bd3ae231605b61ce16621519c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1771331072

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "263M"
zstd_bytes = 274737398

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211210"
previous_tag = "2021-12-10"
previous_file = "rust_arm64_2021-12-10_00-15-rootfs.tar.zst"
previous_sha256 = "4a6ea872f4c2125114ce9c8420009061a022a943ad1b3a9eedf2ef29361b11bd"

current_version = "latest02"
current_date = "20211213"
old_file = "rust_arm64_2021-12-06_10-41-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2021-12-13_00-15-rootfs.tar.zst
# SHA256SUM=f5a493e2f9e997323c823c590ca289b716df7d9bd3ae231605b61ce16621519c
# BUILD_DATE=20211213
# BUILD_TAG=2021-12-13
# STATUS=completed
# VERSION=latest02
# END_TIME=00:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-13
begin = 2021-12-13 00:02:25.972386777+00:00
start-sync_0 = 00:08:38
start-zstd = 00:09:43
start-sync_1 = 00:15:32
end-sync_1 = 00:15:52
end = 2021-12-13 00:15:52.364480804+00:00

[server]
repo = "cake233/rust-arm64"

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
cargo = 'cargo 1.58.0-nightly (40dc28175 2021-12-06)'
rustc = 'rustc 1.59.0-nightly (928783de6 2021-12-11)'
cc = 'cc (Debian 11.2.0-12) 11.2.0'
cargo_verbose = '''
cargo 1.58.0-nightly (40dc28175 2021-12-06)
release: 1.58.0
commit-hash: 40dc281755137ee804bc9b3b08e782773b726e44
commit-date: 2021-12-06
host: aarch64-unknown-linux-gnu
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.59.0-nightly (928783de6 2021-12-11)
binary: rustc
commit-hash: 928783de663bd855a96f14b2d38c1061603587c6
commit-date: 2021-12-11
host: aarch64-unknown-linux-gnu
release: 1.59.0-nightly
LLVM version: 13.0.0
'''
```
