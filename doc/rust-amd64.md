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
tag = ["latest", "2021-11-27", "nightly", "unstable", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

# If the value is false, then the container will not be downloaded.
completed = true

[file]
name = "rust-amd64_2021-11-27_23-36.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "c0ecb37fa711bd4ef256d2ec565b621fe54ceafa8b8298dec4df15148e1c434f"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "885M"
tar-bytes = 927336448

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "248M"
zstd-bytes = 259586409

[compatibility]
compatible_mode = true
rootfs_version = "latest02"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-amd64_2021-11-27_23-36.tar.zst
# BUILD_DATE=20211127
# STATUS=completed
# VERSION=latest02
# END_TIME=23:36

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-27 23:33:53.554968107+00:00
start-sync_0 = 23:34:55
start-zstd = 23:35:33
start-sync_1 = 23:36:24
end-sync_1 = 23:36:46
end = 2021-11-27 23:36:46.442300672+00:00

[server]
name = "docker"
node = 4
repo = "cake233/rust-amd64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.58.0-nightly (7f08ace4f 2021-11-24)'
rustc = 'rustc 1.58.0-nightly (6d246f0c8 2021-11-26)'
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
rustc 1.58.0-nightly (6d246f0c8 2021-11-26)
binary: rustc
commit-hash: 6d246f0c8d3063fea86abbb65a824362709541ba
commit-date: 2021-11-26
host: x86_64-unknown-linux-gnu
release: 1.58.0-nightly
LLVM version: 13.0.0
'''
```
