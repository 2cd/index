# rust-amd64

## How to run it?

```shell
docker run \
    -it \
    --name rust-amd64 \
    cake233/rust-amd64
```

## How to exec shell?

```shell
    docker exec -it rust-amd64 bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/rs-project:/app \
    -w /app \
    rust-amd64 \
    cargo b --release
```

## rust-amd64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2021-11-28", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "rust_amd64_2021-11-28_23-11.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "3c33fcff69657665e0db5c20527bb859978a22a17a0d16641803cc38456c7505"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1525985792

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "229M"
zstd_bytes = 239122593

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211128"
last_tag = ""
last_file = ""

current_version = "latest01"
current_date = "20211128"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2021-11-28_23-11.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest01
# END_TIME=23:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 23:03:26.292408594+00:00
start-sync_0 = 23:04:48
start-zstd = 23:05:46
start-sync_1 = 23:11:00
end-sync_1 = 23:11:23
end = 2021-11-28 23:11:23.663707992+00:00

[server]
repo = "cake233/rust-amd64"

[server.node1]
name = "cn"
current = false
last = true
split = false

[server.node2]
name = "us"
current = false
last = true
split = false
part = 12

[server.node3]
name = "global"
current = false
last = true
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
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.58.0-nightly (7f08ace4f 2021-11-24)'
rustc = 'rustc 1.59.0-nightly (686e313a9 2021-11-27)'
cc = 'cc (Debian 11.2.0-12) 11.2.0'
cargo_verbose = '''
cargo 1.58.0-nightly (7f08ace4f 2021-11-24)
release: 1.58.0
commit-hash: 7f08ace4f1305de7f3b1b0e2f765911957226bd4
commit-date: 2021-11-24
host: x86_64-unknown-linux-gnu
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: OracleLinux [64-bit]
'''
rustc_verbose = '''
rustc 1.59.0-nightly (686e313a9 2021-11-27)
binary: rustc
commit-hash: 686e313a9aa14107c8631ffe48fa09110a7692db
commit-date: 2021-11-27
host: x86_64-unknown-linux-gnu
release: 1.59.0-nightly
LLVM version: 13.0.0
'''
```
