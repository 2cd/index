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
tag = ["latest", "2022-07-01", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2022-07-01_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2eac6b2b5caeaf3a671893f2e26b13959663301d5778b107979d87f9f5c30c2b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1726528512

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "233M"
zstd_bytes = 243765546

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220627"
previous_tag = "2022-06-27"
previous_file = "rust_ppc64el_2022-06-27_03-06-rootfs.tar.zst"
previous_sha256 = "f9d78304b2434f1d4ef7d18d0da8f6230895d715337c276a53edc1d2321cb97a"

current_version = "latest01"
current_date = "20220701"
old_file = "rust_ppc64el_2022-06-24_03-10-rootfs.tar.zst"
old_sha256 = "e9b051318397493c90d0c3e31d4871d81714e87fa4d5940fba8767b94b5edcf4"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2022-07-01_03-05-rootfs.tar.zst
# SHA256SUM=2eac6b2b5caeaf3a671893f2e26b13959663301d5778b107979d87f9f5c30c2b
# BUILD_DATE=20220701
# BUILD_TAG=2022-07-01
# STATUS=completed
# VERSION=latest01
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-01
begin = 2022-07-01 02:52:29.014659426+00:00
start-sync_0 = 02:58:56
start-zstd = 02:59:52
start-sync_1 = 03:05:13
end-sync_1 = 03:05:34
end = 2022-07-01 03:05:34.701036883+00:00

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
cargo = 'cargo 1.64.0-nightly (dbff32b27 2022-06-24)'
rustc = 'rustc 1.64.0-nightly (7425fb293 2022-06-30)'
cc = 'cc (Debian 11.3.0-4) 11.3.0'
cargo_verbose = '''
cargo 1.64.0-nightly (dbff32b27 2022-06-24)
release: 1.64.0-nightly
commit-hash: dbff32b27893b899ae2397f3d56d1be111041d56
commit-date: 2022-06-24
host: powerpc64le-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.64.0-nightly (7425fb293 2022-06-30)
binary: rustc
commit-hash: 7425fb293f510a6f138e82a963a3bc599a5b9e1c
commit-date: 2022-06-30
host: powerpc64le-unknown-linux-gnu
release: 1.64.0-nightly
LLVM version: 14.0.6
'''
```
