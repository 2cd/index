# rust-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name rust-alpine-arm64 \
    cake233/rust-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it rust-alpine-arm64 bash
```
<!-- repo=cake233/rust-alpine-arm64 -->

## Example

### set env

```sh
_UID="$(id -u)" || _UID=0
_GID="$(id -g)" || _GID=0
```

### create a new project

If "tmp/hello" already exists in the current directory, it can be skipped.

```sh
mkdir -p tmp

docker run \
    -t \
    --rm \
    -u "$_UID":"$_GID" \
    -v "$PWD"/tmp:/app \
    -w /app \
    cake233/rust-alpine-arm64 \
    cargo new hello
```

### cargo build

```sh
docker run \
    -t \
    --rm \
    -u "$_UID":"$_GID" \
    -v "$PWD"/tmp/hello:/app \
    -w /app \
    cake233/rust-alpine-arm64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-alpine-arm64.toml

```toml
[main]
name = "rust"
tag = ["alpine", "2023-09-25", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2023-09-25_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f30ed661b8211493e2e3ef57d1567623e1160acc881362539557736beac1b49f"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "897M"
tar_bytes = 940504064

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "158M"
zstd_bytes = 165532611

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230922"
previous_tag = "2023-09-22"
previous_file = "rust-musl_arm64_2023-09-22_03-01-rootfs.tar.zst"
previous_sha256 = "0c42ae996abb7aee93c4f9db5fd07097db3ef258308601a3ad61b404e891b8c8"

current_version = "latest02"
current_date = "20230925"
old_file = "rust-musl_arm64_2023-09-15_03-00-rootfs.tar.zst"
old_sha256 = "31d790422d7df24ea082d99cb864e6445830deb5e5526594594225af21940db0"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2023-09-25_03-00-rootfs.tar.zst
# SHA256SUM=f30ed661b8211493e2e3ef57d1567623e1160acc881362539557736beac1b49f
# BUILD_DATE=20230925
# BUILD_TAG=2023-09-25
# STATUS=completed
# VERSION=latest02
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-25
begin = 2023-09-25 02:52:30.134867774+00:00
start-sync_0 = 02:54:38
start-zstd = 02:55:15
start-sync_1 = 03:00:32
end-sync_1 = 03:00:50
end = 2023-09-25 03:00:50.974855569+00:00

[server]
repo = "cake233/rust-alpine-arm64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = true
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = true
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
ldd = 'musl libc (aarch64) Version 1.2.4_git20230717'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.74.0-nightly (414d9e3a6 2023-09-22)'
rustc = 'rustc 1.74.0-nightly (37390d656 2023-09-24)'
cc = 'cc (Alpine 13.1.1_git20230722) 13.1.1 20230722'
cargo_verbose = '''
cargo 1.74.0-nightly (414d9e3a6 2023-09-22)
release: 1.74.0-nightly
commit-hash: 414d9e3a6d8096f3e276234ce220c868767a8792
commit-date: 2023-09-22
host: aarch64-unknown-linux-musl
libgit2: 1.7.1 (sys:0.18.0 vendored)
libcurl: 8.3.0-DEV (sys:0.4.66+curl-8.3.0 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Alpine Linux 3.19_alpha20230901 [64-bit]
'''
rustc_verbose = '''
rustc 1.74.0-nightly (37390d656 2023-09-24)
binary: rustc
commit-hash: 37390d65636dd67e263753a3c04fbc60dcc4348e
commit-date: 2023-09-24
host: aarch64-unknown-linux-musl
release: 1.74.0-nightly
LLVM version: 17.0.0
'''
```
