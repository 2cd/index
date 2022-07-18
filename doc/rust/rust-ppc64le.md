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
tag = ["latest", "2022-07-18", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2022-07-18_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "924b0069887a7a31c1aa67a2164181f0c143a53b1fc7437f1b8e7eb7a44cb416"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1753827328

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "238M"
zstd_bytes = 248974306

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220711"
previous_tag = "2022-07-11"
previous_file = "rust_ppc64el_2022-07-11_03-06-rootfs.tar.zst"
previous_sha256 = "0dfa18734990404452821add21721a27096f9c85b06473b19686d45a726c7d6f"

current_version = "latest01"
current_date = "20220718"
old_file = "rust_ppc64el_2022-07-08_03-09-rootfs.tar.zst"
old_sha256 = "6578dafd5c710c2ca79fab7f9cab3c04c67395c4ea016c4a0b6e08819f74fe64"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2022-07-18_03-06-rootfs.tar.zst
# SHA256SUM=924b0069887a7a31c1aa67a2164181f0c143a53b1fc7437f1b8e7eb7a44cb416
# BUILD_DATE=20220718
# BUILD_TAG=2022-07-18
# STATUS=completed
# VERSION=latest01
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-18
begin = 2022-07-18 02:52:31.343891276+00:00
start-sync_0 = 02:59:08
start-zstd = 03:00:09
start-sync_1 = 03:05:50
end-sync_1 = 03:06:13
end = 2022-07-18 03:06:13.864389152+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-8) 2.33'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.64.0-nightly (8827baaa7 2022-07-14)'
rustc = 'rustc 1.64.0-nightly (263edd43c 2022-07-17)'
cc = 'cc (Debian 11.3.0-4) 11.3.0'
cargo_verbose = '''
cargo 1.64.0-nightly (8827baaa7 2022-07-14)
release: 1.64.0-nightly
commit-hash: 8827baaa781b37872134c1ba692a6f0aeb37890e
commit-date: 2022-07-14
host: powerpc64le-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.64.0-nightly (263edd43c 2022-07-17)
binary: rustc
commit-hash: 263edd43c5255084292329423c61a9d69715ebfa
commit-date: 2022-07-17
host: powerpc64le-unknown-linux-gnu
release: 1.64.0-nightly
LLVM version: 14.0.6
'''
```
