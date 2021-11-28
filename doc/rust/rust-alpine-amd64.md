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
    rust-alpine-amd64 \
    cargo b --release
```

## rust-alpine-amd64.toml

```toml
[main]
name = "rust"
tag = ["alpine", "2021-11-28", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "rust-alpine-amd64_2021-11-28_22-29.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "8aadf34dcd106597c374ad123feab5e7d1ad151ed25b8c3c1986688d800ef84b"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "838M"
tar_bytes = 878290944

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "191M"
zstd_bytes = 199544510

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
# ROOTFS_FILE=rust-alpine-amd64_2021-11-28_22-29.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest01
# END_TIME=22:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 22:25:54.046897079+00:00
start-sync_0 = 22:26:32
start-zstd = 22:27:17
start-sync_1 = 22:29:40
end-sync_1 = 22:29:59
end = 2021-11-28 22:29:59.511487898+00:00

[server]
repo = "cake233/rust-alpine-amd64"

[server.node1]
name = "cn"
current = false
last = true
split = false

[server.node2]
name = "us"
current = false
last = false
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
rustup = 'rustup 1.24.3 (2021-05-31)'
cargo = 'cargo 1.58.0-nightly (7f08ace4f 2021-11-24)'
rustc = 'rustc 1.59.0-nightly (686e313a9 2021-11-27)'
cc = 'cc (Alpine 11.2.1_git20211125) 11.2.1 20211125'
cargo_verbose = '''
cargo 1.58.0-nightly (7f08ace4f 2021-11-24)
release: 1.58.0
commit-hash: 7f08ace4f1305de7f3b1b0e2f765911957226bd4
commit-date: 2021-11-24
host: x86_64-unknown-linux-musl
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Alpine Linux 3.15.0_alpha20210804 [64-bit]
'''
rustc_verbose = '''
rustc 1.59.0-nightly (686e313a9 2021-11-27)
binary: rustc
commit-hash: 686e313a9aa14107c8631ffe48fa09110a7692db
commit-date: 2021-11-27
host: x86_64-unknown-linux-musl
release: 1.59.0-nightly
LLVM version: 13.0.0
'''
```
