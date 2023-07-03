# rust-armv7

## How to run it?

```sh
docker run \
    -it \
    --name rust-armv7 \
    cake233/rust-armv7
```

## How to exec shell?

```sh
docker exec -it rust-armv7 bash
```
<!-- repo=cake233/rust-armv7 -->

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
    cake233/rust-armv7 \
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
    cake233/rust-armv7 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-armv7.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-07-03", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-07-03_03-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "93713ab545e055d6bc8b328d11d9b1f60babe9f964fbb839f6d85ca150f254f5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1532823552

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "219M"
zstd_bytes = 228804228

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230630"
previous_tag = "2023-06-30"
previous_file = "rust_armhf_2023-06-30_03-06-rootfs.tar.zst"
previous_sha256 = "67ba76c786fd86ebb82e3b5489f13584cf77288880d851f121165a09af783150"

current_version = "latest01"
current_date = "20230703"
old_file = "rust_armhf_2023-06-26_03-05-rootfs.tar.zst"
old_sha256 = "d5451c865cdfbc4c58cdd60a8c02dfaee04ba122b7a9afe913adc6cb96100f3d"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-07-03_03-03-rootfs.tar.zst
# SHA256SUM=93713ab545e055d6bc8b328d11d9b1f60babe9f964fbb839f6d85ca150f254f5
# BUILD_DATE=20230703
# BUILD_TAG=2023-07-03
# STATUS=completed
# VERSION=latest01
# END_TIME=03:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-03
begin = 2023-07-03 02:52:32.828319833+00:00
start-sync_0 = 02:58:26
start-zstd = 02:59:20
start-sync_1 = 03:03:42
end-sync_1 = 03:03:59
end = 2023-07-03 03:03:59.490381265+00:00

[server]
repo = "cake233/rust-armv7"

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
ldd = 'ldd (Debian GLIBC 2.37-3) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.72.0-nightly (5b377cece 2023-06-30)'
rustc = 'rustc 1.72.0-nightly (839e9a6e1 2023-07-02)'
cc = 'cc (Debian 12.3.0-5) 12.3.0'
cargo_verbose = '''
cargo 1.72.0-nightly (5b377cece 2023-06-30)
release: 1.72.0-nightly
commit-hash: 5b377cece0e0dd0af686cf53ce4637d5d85c2a10
commit-date: 2023-06-30
host: armv7-unknown-linux-gnueabihf
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.72.0-nightly (839e9a6e1 2023-07-02)
binary: rustc
commit-hash: 839e9a6e1210934fd24b15548b811a97c77138fc
commit-date: 2023-07-02
host: armv7-unknown-linux-gnueabihf
release: 1.72.0-nightly
LLVM version: 16.0.5
'''
```
