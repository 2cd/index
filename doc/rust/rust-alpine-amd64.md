# rust-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name rust-alpine-amd64 \
    cake233/rust-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it rust-alpine-amd64 bash
```
<!-- repo=cake233/rust-alpine-amd64 -->

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
    cake233/rust-alpine-amd64 \
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
    cake233/rust-alpine-amd64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-alpine-amd64.toml

```toml
[main]
name = "rust"
tag = ["alpine", "2022-12-05", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2022-12-05_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5683071b5dc76826a81f8b0a25cac0b197ef662f65f366b64c705aaf97be097d"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "812M"
tar_bytes = 850578432

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "164M"
zstd_bytes = 171189372

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221202"
previous_tag = "2022-12-02"
previous_file = "rust-musl_amd64_2022-12-02_02-59-rootfs.tar.zst"
previous_sha256 = "a5f4d28194cbaab2c75140881f05f1d7635c075b7e8b7f65b206ea4383404392"

current_version = "latest01"
current_date = "20221205"
old_file = "rust-musl_amd64_2022-11-28_02-59-rootfs.tar.zst"
old_sha256 = "9c69f5f193e14efe551f8a790c87a1b87f1607977c70d2741d0caba4a5ae74b5"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2022-12-05_02-59-rootfs.tar.zst
# SHA256SUM=5683071b5dc76826a81f8b0a25cac0b197ef662f65f366b64c705aaf97be097d
# BUILD_DATE=20221205
# BUILD_TAG=2022-12-05
# STATUS=completed
# VERSION=latest01
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-05
begin = 2022-12-05 02:52:26.770973577+00:00
start-sync_0 = 02:53:23
start-zstd = 02:54:06
start-sync_1 = 02:59:10
end-sync_1 = 02:59:26
end = 2022-12-05 02:59:26.602726851+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.3'
rustup = 'rustup 1.25.1 (2022-07-12)'
cargo = 'cargo 1.67.0-nightly (f6e737b1e 2022-12-02)'
rustc = 'rustc 1.67.0-nightly (53e4b9dd7 2022-12-04)'
cc = 'cc (Alpine 12.2.1_git20220924-r4) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.67.0-nightly (f6e737b1e 2022-12-02)
release: 1.67.0-nightly
commit-hash: f6e737b1e3386adb89333bf06a01f68a91ac5306
commit-date: 2022-12-02
host: x86_64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.17_alpha20221110 [64-bit]
'''
rustc_verbose = '''
rustc 1.67.0-nightly (53e4b9dd7 2022-12-04)
binary: rustc
commit-hash: 53e4b9dd74c29cc9308b8d0f10facac70bb101a7
commit-date: 2022-12-04
host: x86_64-unknown-linux-musl
release: 1.67.0-nightly
LLVM version: 15.0.4
'''
```
