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
tag = ["alpine", "2023-01-09", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2023-01-09_03-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2fe9a792444b4bb9b306f5af4e2b8243e73858c98619dc03d72eb8973cf21fa7"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "854M"
tar_bytes = 895452672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "155M"
zstd_bytes = 162267229

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230106"
previous_tag = "2023-01-06"
previous_file = "rust-musl_arm64_2023-01-06_03-01-rootfs.tar.zst"
previous_sha256 = "31a5845d130c535d409c5a9ae5c4156640983506d1dcc30b51a1b8400aed6f86"

current_version = "latest02"
current_date = "20230109"
old_file = "rust-musl_arm64_2023-01-02_03-00-rootfs.tar.zst"
old_sha256 = "17b5548377df8ef831a10ab4f9199f412ff6adc85038c223adb964e677c1c296"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2023-01-09_03-01-rootfs.tar.zst
# SHA256SUM=2fe9a792444b4bb9b306f5af4e2b8243e73858c98619dc03d72eb8973cf21fa7
# BUILD_DATE=20230109
# BUILD_TAG=2023-01-09
# STATUS=completed
# VERSION=latest02
# END_TIME=03:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-09
begin = 2023-01-09 02:52:27.000874621+00:00
start-sync_0 = 02:54:38
start-zstd = 02:55:26
start-sync_1 = 03:00:49
end-sync_1 = 03:01:07
end = 2023-01-09 03:01:07.373283385+00:00

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
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.68.0-nightly (8c460b223 2023-01-04)'
rustc = 'rustc 1.68.0-nightly (cc47b0699 2023-01-08)'
cc = 'cc (Alpine 12.2.1_git20220924-r7) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.68.0-nightly (8c460b223 2023-01-04)
release: 1.68.0-nightly
commit-hash: 8c460b2237a6359a7e3335890db8da049bdd62fc
commit-date: 2023-01-04
host: aarch64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.17_alpha20221110 [64-bit]
'''
rustc_verbose = '''
rustc 1.68.0-nightly (cc47b0699 2023-01-08)
binary: rustc
commit-hash: cc47b069983292e4ee8982d5dabe6301452c5f25
commit-date: 2023-01-08
host: aarch64-unknown-linux-musl
release: 1.68.0-nightly
LLVM version: 15.0.6
'''
```
