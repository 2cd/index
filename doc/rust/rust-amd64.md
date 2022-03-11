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
tag = ["latest", "2022-03-11", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "rust_amd64_2022-03-11_03-00.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "4241c39d3fb0f6e1014e82826a4d871507e775d91a76ea22e480befa7efb1fe4"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1567236608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "232M"
zstd_bytes = 243224831

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220307"
previous_tag = "2022-03-07"
previous_file = "rust_amd64_2022-03-07_03-00-rootfs.tar.zst"
previous_sha256 = "71c67454ca09bbea64018b201722d834d9bcb719aedd2c81a13d4c38349ca39d"

current_version = "latest02"
current_date = "20220311"
old_file = "rust_amd64_2022-03-04_03-00-rootfs.tar.zst"
old_sha256 = "58322e6b71557bed1c4148bfcefe4cab1cdbd257a04d29360ab6d95bbfa2bf09"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2022-03-11_03-00-rootfs.tar.zst
# SHA256SUM=4241c39d3fb0f6e1014e82826a4d871507e775d91a76ea22e480befa7efb1fe4
# BUILD_DATE=20220311
# BUILD_TAG=2022-03-11
# STATUS=completed
# VERSION=latest02
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-11
begin = 2022-03-11 02:52:26.679283280+00:00
start-sync_0 = 02:53:59
start-zstd = 02:54:55
start-sync_1 = 03:00:03
end-sync_1 = 03:00:25
end = 2022-03-11 03:00:25.458715241+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.61.0-nightly (65c8266 2022-03-09)'
rustc = 'rustc 1.61.0-nightly (5f4e06771 2022-03-10)'
cc = 'cc (Debian 11.2.0-18) 11.2.0'
cargo_verbose = '''
cargo 1.61.0-nightly (65c8266 2022-03-09)
release: 1.61.0-nightly
commit-hash: 65c82664263feddc5fe2d424be0993c28d46377a
commit-date: 2022-03-09
host: x86_64-unknown-linux-gnu
libgit2: 1.4.1 (sys:0.14.1 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: OracleLinux [64-bit]
'''
rustc_verbose = '''
rustc 1.61.0-nightly (5f4e06771 2022-03-10)
binary: rustc
commit-hash: 5f4e0677190b82e61dc507e3e72caf89da8e5e28
commit-date: 2022-03-10
host: x86_64-unknown-linux-gnu
release: 1.61.0-nightly
LLVM version: 14.0.0
'''
```
