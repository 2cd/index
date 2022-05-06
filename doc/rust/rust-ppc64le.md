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
tag = ["latest", "2022-05-06", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2022-05-06_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "dcfadadce8e68bbc33b9be5e1a50fce7e7a31b5528c1f7c1e1e9ace412039e55"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1716801024

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "230M"
zstd_bytes = 240626842

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220502"
previous_tag = "2022-05-02"
previous_file = "rust_ppc64el_2022-05-02_03-05-rootfs.tar.zst"
previous_sha256 = "8e1a5b42b9e2a370de3d143e271726640511bac4c1ba74066e14013cea3c648e"

current_version = "latest02"
current_date = "20220506"
old_file = "rust_ppc64el_2022-04-29_03-05-rootfs.tar.zst"
old_sha256 = "a99051fde37053b573889c67a288ef6b6e3a699a857f592071ab0e274ae64bb6"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2022-05-06_03-05-rootfs.tar.zst
# SHA256SUM=dcfadadce8e68bbc33b9be5e1a50fce7e7a31b5528c1f7c1e1e9ace412039e55
# BUILD_DATE=20220506
# BUILD_TAG=2022-05-06
# STATUS=completed
# VERSION=latest02
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-06
begin = 2022-05-06 02:52:43.561101096+00:00
start-sync_0 = 02:59:04
start-zstd = 03:00:03
start-sync_1 = 03:05:28
end-sync_1 = 03:05:47
end = 2022-05-06 03:05:47.771913929+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.62.0-nightly (a44758ac8 2022-05-04)'
rustc = 'rustc 1.62.0-nightly (30f386087 2022-05-05)'
cc = 'cc (Debian 11.3.0-1) 11.3.0'
cargo_verbose = '''
cargo 1.62.0-nightly (a44758ac8 2022-05-04)
release: 1.62.0-nightly
commit-hash: a44758ac805600edbb6ba51e7e6fb81a6077c0cd
commit-date: 2022-05-04
host: powerpc64le-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1n)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.62.0-nightly (30f386087 2022-05-05)
binary: rustc
commit-hash: 30f386087564243ab88a93c984c265290a31580b
commit-date: 2022-05-05
host: powerpc64le-unknown-linux-gnu
release: 1.62.0-nightly
LLVM version: 14.0.1
'''
```
