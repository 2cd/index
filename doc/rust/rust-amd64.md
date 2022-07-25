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
tag = ["latest", "2022-07-25", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2022-07-25_03-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "26b2fe558007f5380f81a9277d946f7d5ffe4f736655e4a75f358f57dc6293b2"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.9G"
tar_bytes = 1962491392

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "339M"
zstd_bytes = 355248635

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220718"
previous_tag = "2022-07-18"
previous_file = "rust_amd64_2022-07-18_03-00-rootfs.tar.zst"
previous_sha256 = "db9ac467e42ce5b7fa8fd294c3184da0ce56cea2c63824bf247c2e28602cc34d"

current_version = "latest01"
current_date = "20220725"
old_file = "rust_amd64_2022-07-15_03-01-rootfs.tar.zst"
old_sha256 = "d314d912295a4d94762b3d665b44025a87e97bacf59126606e92ec93fa42bbd6"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2022-07-25_03-03-rootfs.tar.zst
# SHA256SUM=26b2fe558007f5380f81a9277d946f7d5ffe4f736655e4a75f358f57dc6293b2
# BUILD_DATE=20220725
# BUILD_TAG=2022-07-25
# STATUS=completed
# VERSION=latest01
# END_TIME=03:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-25
begin = 2022-07-25 02:52:28.133778318+00:00
start-sync_0 = 02:54:27
start-zstd = 02:55:37
start-sync_1 = 03:03:26
end-sync_1 = 03:03:53
end = 2022-07-25 03:03:54.015806926+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-8) 2.33'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.64.0-nightly (d8d30a753 2022-07-19)'
rustc = 'rustc 1.64.0-nightly (7fe022f5a 2022-07-24)'
cc = 'cc (Debian 12.1.0-7) 12.1.0'
cargo_verbose = '''
cargo 1.64.0-nightly (d8d30a753 2022-07-19)
release: 1.64.0-nightly
commit-hash: d8d30a75376f78bb0fabe3d28ee9d87aa8035309
commit-date: 2022-07-19
host: x86_64-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: OracleLinux [64-bit]
'''
rustc_verbose = '''
rustc 1.64.0-nightly (7fe022f5a 2022-07-24)
binary: rustc
commit-hash: 7fe022f5aa32bbbb33c3a58755729d6667a461a9
commit-date: 2022-07-24
host: x86_64-unknown-linux-gnu
release: 1.64.0-nightly
LLVM version: 14.0.6
'''
```
