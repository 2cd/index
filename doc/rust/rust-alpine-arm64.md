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
tag = ["alpine", "2022-06-17", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2022-06-17_03-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2ff538e265b4e272c7c29f473225d158d3d598abe6f00cd60a1246f2a7ed33fa"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "761M"
tar_bytes = 797844992

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "145M"
zstd_bytes = 151459836

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220613"
previous_tag = "2022-06-13"
previous_file = "rust-musl_arm64_2022-06-13_03-00-rootfs.tar.zst"
previous_sha256 = "a1e28dee9ac5d4375f8df6410ad15168c69740f2a14a3e42737481c30fcd490f"

current_version = "latest01"
current_date = "20220617"
old_file = "rust-musl_arm64_2022-06-10_03-01-rootfs.tar.zst"
old_sha256 = "236e8b15f237a37c491d1e8289693034a5a34eddcdac8c9c8eccaac659e5138d"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2022-06-17_03-01-rootfs.tar.zst
# SHA256SUM=2ff538e265b4e272c7c29f473225d158d3d598abe6f00cd60a1246f2a7ed33fa
# BUILD_DATE=20220617
# BUILD_TAG=2022-06-17
# STATUS=completed
# VERSION=latest01
# END_TIME=03:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-17
begin = 2022-06-17 02:52:36.797872368+00:00
start-sync_0 = 02:54:40
start-zstd = 02:55:45
start-sync_1 = 03:00:54
end-sync_1 = 03:01:09
end = 2022-06-17 03:01:09.717542415+00:00

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
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.63.0-nightly (4d92f07f3 2022-06-09)'
rustc = 'rustc 1.63.0-nightly (cacc75c82 2022-06-16)'
cc = 'cc (Alpine 11.2.1_git20220219) 11.2.1 20220219'
cargo_verbose = '''
cargo 1.63.0-nightly (4d92f07f3 2022-06-09)
release: 1.63.0-nightly
commit-hash: 4d92f07f34ba7fb7d7f207564942508f46c225d3
commit-date: 2022-06-09
host: aarch64-unknown-linux-musl
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Alpine Linux 3.16.0_alpha20220328 [64-bit]
'''
rustc_verbose = '''
rustc 1.63.0-nightly (cacc75c82 2022-06-16)
binary: rustc
commit-hash: cacc75c82ebe15cf63d31034fcf7f1016cddf0e2
commit-date: 2022-06-16
host: aarch64-unknown-linux-musl
release: 1.63.0-nightly
LLVM version: 14.0.5
'''
```
