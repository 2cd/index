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
tag = ["latest", "2022-09-05", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2022-09-05_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2008510f097c3614d5fcf18ce4453910007caa790305744e3631c159bb25edeb"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1782161408

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "247M"
zstd_bytes = 258557581

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220902"
previous_tag = "2022-09-02"
previous_file = "rust_ppc64el_2022-09-02_03-09-rootfs.tar.zst"
previous_sha256 = "209b6258a3c92c3dccfe259fc8b0d5c30ee020973c79c50e8fe704d6836b0aaf"

current_version = "latest01"
current_date = "20220905"
old_file = "rust_ppc64el_2022-08-29_03-10-rootfs.tar.zst"
old_sha256 = "d0e6a27fb76fa51591c0960d5d99c4d28f6ecda1984b1d3e6ff79005d8ea7ce5"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2022-09-05_03-06-rootfs.tar.zst
# SHA256SUM=2008510f097c3614d5fcf18ce4453910007caa790305744e3631c159bb25edeb
# BUILD_DATE=20220905
# BUILD_TAG=2022-09-05
# STATUS=completed
# VERSION=latest01
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-05
begin = 2022-09-05 02:52:18.722693734+00:00
start-sync_0 = 02:58:55
start-zstd = 02:59:53
start-sync_1 = 03:05:45
end-sync_1 = 03:06:05
end = 2022-09-05 03:06:05.817372670+00:00

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
ldd = 'ldd (Debian GLIBC 2.34-7) 2.34'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.65.0-nightly (4ed54cecc 2022-08-27)'
rustc = 'rustc 1.65.0-nightly (289279de1 2022-09-04)'
cc = 'cc (Debian 12.2.0-1) 12.2.0'
cargo_verbose = '''
cargo 1.65.0-nightly (4ed54cecc 2022-08-27)
release: 1.65.0-nightly
commit-hash: 4ed54cecce3ce9ab6ff058781f4c8a500ee6b8b5
commit-date: 2022-08-27
host: powerpc64le-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.65.0-nightly (289279de1 2022-09-04)
binary: rustc
commit-hash: 289279de116707f28cf9c18e4bbb8c6ec84ad75b
commit-date: 2022-09-04
host: powerpc64le-unknown-linux-gnu
release: 1.65.0-nightly
LLVM version: 15.0.0
'''
```
