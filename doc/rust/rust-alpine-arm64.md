# rust-alpine-arm64

## How to run it?

```shell
docker run \
    -it \
    --name rust-alpine-arm64 \
    cake233/rust-alpine-arm64
```

## How to exec shell?

```shell
    docker exec -it rust-alpine-arm64 bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/rs-project:/app \
    -w /app \
    cake233/rust-alpine-arm64 \
    cargo b --release
```

## rust-alpine-arm64.toml

```toml
[main]
name = "rust"
tag = ["alpine", "2021-11-29", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "rust-musl_arm64_2021-11-29_00-33.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "601a991924566e7f078893e8a87cae0fb7fb242cc848ff723799a864c3c3ad98"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "787M"
tar_bytes = 825146880

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "182M"
zstd_bytes = 190660211

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211101"
last_tag = ""
last_file = "rust_arm64+alpine-2021_11-01-rootfs.tar.zst"

current_version = "latest01"
current_date = "20211129"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2021-11-29_00-33-rootfs.tar.zst
# BUILD_DATE=20211129
# BUILD_TAG=2021-11-29
# STATUS=completed
# VERSION=latest01
# END_TIME=00:33

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-29
begin = 2021-11-29 00:27:05.466229314+00:00
start-sync_0 = 00:29:45
start-zstd = 00:30:29
start-sync_1 = 00:32:59
end-sync_1 = 00:33:21
end = 2021-11-29 00:33:21.074352689+00:00

[server]
repo = "cake233/rust-alpine-arm64"

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
LANG = "C.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.58.0-nightly (7f08ace4f 2021-11-24)'
rustc = 'rustc 1.59.0-nightly (686e313a9 2021-11-27)'
cc = 'cc (Alpine 11.2.1_git20211125) 11.2.1 20211125'
cargo_verbose = '''
cargo 1.58.0-nightly (7f08ace4f 2021-11-24)
release: 1.58.0
commit-hash: 7f08ace4f1305de7f3b1b0e2f765911957226bd4
commit-date: 2021-11-24
host: aarch64-unknown-linux-musl
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Alpine Linux 3.15.0_alpha20210804 [64-bit]
'''
rustc_verbose = '''
rustc 1.59.0-nightly (686e313a9 2021-11-27)
binary: rustc
commit-hash: 686e313a9aa14107c8631ffe48fa09110a7692db
commit-date: 2021-11-27
host: aarch64-unknown-linux-musl
release: 1.59.0-nightly
LLVM version: 13.0.0
'''
```
