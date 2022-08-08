# rust-ppc64le

## How to run it?

```sh
docker run \
    -it \
    --name rust-ppc64le \
    cake233/rust-ppc64le
```

## How to exec shell?

```sh
docker exec -it rust-ppc64le bash
```
<!-- repo=cake233/rust-ppc64le -->

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
    cake233/rust-ppc64le \
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
    cake233/rust-ppc64le \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-ppc64le.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-08-08", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2022-08-08_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "073aba834289a8b50a08f70b0d6b6fccf33782d12b6053ffb2c4691622cefa59"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.0G"
tar_bytes = 2053229568

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "331M"
zstd_bytes = 346315492

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220805"
previous_tag = "2022-08-05"
previous_file = "rust_ppc64el_2022-08-05_03-12-rootfs.tar.zst"
previous_sha256 = "6a9b59dedfcec456e172460722c0c2e8afb1dd7e191df53aa1b92d3cef5147f4"

current_version = "latest01"
current_date = "20220808"
old_file = "rust_ppc64el_2022-07-18_03-06-rootfs.tar.zst"
old_sha256 = "924b0069887a7a31c1aa67a2164181f0c143a53b1fc7437f1b8e7eb7a44cb416"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2022-08-08_03-06-rootfs.tar.zst
# SHA256SUM=073aba834289a8b50a08f70b0d6b6fccf33782d12b6053ffb2c4691622cefa59
# BUILD_DATE=20220808
# BUILD_TAG=2022-08-08
# STATUS=completed
# VERSION=latest01
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-08
begin = 2022-08-08 02:52:20.149597556+00:00
start-sync_0 = 02:59:01
start-zstd = 02:59:59
start-sync_1 = 03:06:26
end-sync_1 = 03:06:50
end = 2022-08-08 03:06:50.589210859+00:00

[server]
repo = "cake233/rust-ppc64le"

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
ldd = 'ldd (Debian GLIBC 2.34-1) 2.34'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.65.0-nightly (4fd148c47 2022-08-03)'
rustc = 'rustc 1.65.0-nightly (d394408fb 2022-08-07)'
cc = 'cc (Debian 12.1.0-7) 12.1.0'
cargo_verbose = '''
cargo 1.65.0-nightly (4fd148c47 2022-08-03)
release: 1.65.0-nightly
commit-hash: 4fd148c47e733770c537efac5220744945d572ef
commit-date: 2022-08-03
host: powerpc64le-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.65.0-nightly (d394408fb 2022-08-07)
binary: rustc
commit-hash: d394408fb38c4de61f765a3ed5189d2731a1da91
commit-date: 2022-08-07
host: powerpc64le-unknown-linux-gnu
release: 1.65.0-nightly
LLVM version: 14.0.6
'''
```
