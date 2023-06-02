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
tag = ["alpine", "2023-06-02", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2023-06-02_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "53fba23416087094eb5d6999016e57db6c479bb497b0dc835f5096c65db5781c"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "809M"
tar_bytes = 847433216

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "163M"
zstd_bytes = 170827153

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230529"
previous_tag = "2023-05-29"
previous_file = "rust-musl_amd64_2023-05-29_03-00-rootfs.tar.zst"
previous_sha256 = "c115d760dedd6bc8e1f64abcffb27bedcc0dc3fbdf0cc92d39948c6340cc7ce1"

current_version = "latest01"
current_date = "20230602"
old_file = "rust-musl_amd64_2023-05-26_03-01-rootfs.tar.zst"
old_sha256 = "17dd0f4f999fb340fc17458f9f1d4fd63067d317b3e22d03754166e99e46a1db"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2023-06-02_02-59-rootfs.tar.zst
# SHA256SUM=53fba23416087094eb5d6999016e57db6c479bb497b0dc835f5096c65db5781c
# BUILD_DATE=20230602
# BUILD_TAG=2023-06-02
# STATUS=completed
# VERSION=latest01
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-02
begin = 2023-06-02 02:52:35.555789185+00:00
start-sync_0 = 02:53:22
start-zstd = 02:54:11
start-sync_1 = 02:59:34
end-sync_1 = 02:59:53
end = 2023-06-02 02:59:53.370427324+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.4'
rustup = 'rustup 1.26.0 (2023-04-05)'
cargo = 'cargo 1.72.0-nightly (f7b95e316 2023-05-30)'
rustc = 'rustc 1.72.0-nightly (d59363ad0 2023-06-01)'
cc = 'cc (Alpine 13.1.1_git20230527) 13.1.1 20230527'
cargo_verbose = '''
cargo 1.72.0-nightly (f7b95e316 2023-05-30)
release: 1.72.0-nightly
commit-hash: f7b95e31642e09c2b6eabb18ed75007dda6677a0
commit-date: 2023-05-30
host: x86_64-unknown-linux-musl
libgit2: 1.6.4 (sys:0.17.1 vendored)
libcurl: 8.0.1-DEV (sys:0.4.61+curl-8.0.1 vendored ssl:OpenSSL/1.1.1t)
ssl: OpenSSL 1.1.1t  7 Feb 2023
os: Alpine Linux 3.18_alpha20230329 [64-bit]
'''
rustc_verbose = '''
rustc 1.72.0-nightly (d59363ad0 2023-06-01)
binary: rustc
commit-hash: d59363ad0b6391b7fc5bbb02c9ccf9300eef3753
commit-date: 2023-06-01
host: x86_64-unknown-linux-musl
release: 1.72.0-nightly
LLVM version: 16.0.4
'''
```
