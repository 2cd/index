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
tag = ["latest", "2023-10-20", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2023-10-20_03-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8709d172b6e176a1a8e7e451b84b3439727e58b3eb182e38cb154c047886c37d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1841499136

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "215M"
zstd_bytes = 225278678

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231016"
previous_tag = "2023-10-16"
previous_file = "rust_ppc64el_2023-10-16_03-06-rootfs.tar.zst"
previous_sha256 = "9fd3afa6bc752a6ddd82129d801f0cbb17a0898cdbd1843b6e2f1790cd6fa5d0"

current_version = "latest02"
current_date = "20231020"
old_file = "rust_ppc64el_2023-10-13_03-06-rootfs.tar.zst"
old_sha256 = "f3e9559c59fcfb479e5815380f95c6898dd409896665e2a6a41e1970acb1ac32"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2023-10-20_03-07-rootfs.tar.zst
# SHA256SUM=8709d172b6e176a1a8e7e451b84b3439727e58b3eb182e38cb154c047886c37d
# BUILD_DATE=20231020
# BUILD_TAG=2023-10-20
# STATUS=completed
# VERSION=latest02
# END_TIME=03:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-20
begin = 2023-10-20 02:52:34.330125264+00:00
start-sync_0 = 02:59:41
start-zstd = 03:00:51
start-sync_1 = 03:07:04
end-sync_1 = 03:07:28
end = 2023-10-20 03:07:28.572739232+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.75.0-nightly (8eb8acbb1 2023-10-17)'
rustc = 'rustc 1.75.0-nightly (4578435e1 2023-10-19)'
cc = 'cc (Debian 13.2.0-5) 13.2.0'
cargo_verbose = '''
cargo 1.75.0-nightly (8eb8acbb1 2023-10-17)
release: 1.75.0-nightly
commit-hash: 8eb8acbb116e7923ea2ce33a50109933ed5ab375
commit-date: 2023-10-17
host: powerpc64le-unknown-linux-gnu
libgit2: 1.7.1 (sys:0.18.1 vendored)
libcurl: 8.4.0-DEV (sys:0.4.68+curl-8.4.0 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.75.0-nightly (4578435e1 2023-10-19)
binary: rustc
commit-hash: 4578435e1695863d921c7763d5a0add98f8e3869
commit-date: 2023-10-19
host: powerpc64le-unknown-linux-gnu
release: 1.75.0-nightly
LLVM version: 17.0.3
'''
```
