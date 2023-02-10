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
tag = ["alpine", "2023-02-10", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2023-02-10_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "415aaad3d2ba01adb762b7b50d07aee274fe1e5d338f42acbc29e7a95f9628bd"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "857M"
tar_bytes = 898621440

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "155M"
zstd_bytes = 162295375

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230206"
previous_tag = "2023-02-06"
previous_file = "rust-musl_arm64_2023-02-06_03-00-rootfs.tar.zst"
previous_sha256 = "22a708378bf4d1d1c64d5482121491a9e1ca6b2869cb5acbd05bd1ace50fbfe2"

current_version = "latest02"
current_date = "20230210"
old_file = "rust-musl_arm64_2023-02-03_03-02-rootfs.tar.zst"
old_sha256 = "997216e0917687f10a5787974b0d56adf533ed77f819f4311a5e261a1fb65216"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2023-02-10_03-00-rootfs.tar.zst
# SHA256SUM=415aaad3d2ba01adb762b7b50d07aee274fe1e5d338f42acbc29e7a95f9628bd
# BUILD_DATE=20230210
# BUILD_TAG=2023-02-10
# STATUS=completed
# VERSION=latest02
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-10
begin = 2023-02-10 02:52:25.943415187+00:00
start-sync_0 = 02:54:20
start-zstd = 02:55:03
start-sync_1 = 03:00:10
end-sync_1 = 03:00:27
end = 2023-02-10 03:00:27.884032089+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.3'
rustup = 'rustup 1.25.2 (17db695f1 2023-02-01)'
cargo = 'cargo 1.69.0-nightly (82c3bb79e 2023-02-04)'
rustc = 'rustc 1.69.0-nightly (8996ea93b 2023-02-09)'
cc = 'cc (Alpine 12.2.1_git20220924-r9) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.69.0-nightly (82c3bb79e 2023-02-04)
release: 1.69.0-nightly
commit-hash: 82c3bb79e3a19a5164e33819ef81bfc2c984bc56
commit-date: 2023-02-04
host: aarch64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.18_alpha20230208 [64-bit]
'''
rustc_verbose = '''
rustc 1.69.0-nightly (8996ea93b 2023-02-09)
binary: rustc
commit-hash: 8996ea93b6e554148c4286e62b613f12a3ee505c
commit-date: 2023-02-09
host: aarch64-unknown-linux-musl
release: 1.69.0-nightly
LLVM version: 15.0.7
'''
```
