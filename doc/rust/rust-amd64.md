# rust-amd64

## How to run it?

```sh
docker run \
    -it \
    --name rust-amd64 \
    cake233/rust-amd64
```

## How to exec shell?

```sh
docker exec -it rust-amd64 bash
```
<!-- repo=cake233/rust-amd64 -->

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
    cake233/rust-amd64 \
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
    cake233/rust-amd64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-amd64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-06-23", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2023-06-23_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "48ea08dfb9bc83793e8a15a9ea24795750312a9e26921326f9f2e88879a1eea2"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1602615808

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "235M"
zstd_bytes = 246021442

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230619"
previous_tag = "2023-06-19"
previous_file = "rust_amd64_2023-06-19_03-00-rootfs.tar.zst"
previous_sha256 = "b308689674c638e51c7fa940446caaac56de2f9607c16b923af4f82905a4a927"

current_version = "latest01"
current_date = "20230623"
old_file = "rust_amd64_2023-06-16_03-00-rootfs.tar.zst"
old_sha256 = "ac2a87555465fc93c3ea989242844d0cba55b5d99ddbefbcfc0c538130e6b16d"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2023-06-23_03-00-rootfs.tar.zst
# SHA256SUM=48ea08dfb9bc83793e8a15a9ea24795750312a9e26921326f9f2e88879a1eea2
# BUILD_DATE=20230623
# BUILD_TAG=2023-06-23
# STATUS=completed
# VERSION=latest01
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-23
begin = 2023-06-23 02:52:41.342590755+00:00
start-sync_0 = 02:54:27
start-zstd = 02:55:26
start-sync_1 = 03:00:17
end-sync_1 = 03:00:37
end = 2023-06-23 03:00:37.302826945+00:00

[server]
repo = "cake233/rust-amd64"

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
LANG = "en_US.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.72.0-nightly (4cebd130e 2023-06-21)'
rustc = 'rustc 1.72.0-nightly (04075b320 2023-06-22)'
cc = 'cc (Debian 12.3.0-4) 12.3.0'
cargo_verbose = '''
cargo 1.72.0-nightly (4cebd130e 2023-06-21)
release: 1.72.0-nightly
commit-hash: 4cebd130ebca3bc219180a54f3e26cc1b14a91de
commit-date: 2023-06-21
host: x86_64-unknown-linux-gnu
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Debian [64-bit]
'''
rustc_verbose = '''
rustc 1.72.0-nightly (04075b320 2023-06-22)
binary: rustc
commit-hash: 04075b32021932e3e8f6ab55d519b3b3494b6ef9
commit-date: 2023-06-22
host: x86_64-unknown-linux-gnu
release: 1.72.0-nightly
LLVM version: 16.0.5
'''
```
