# rust-mips64le

## How to run it?

```sh
docker run \
    -it \
    --name rust-mips64le \
    cake233/rust-mips64le
```

## How to exec shell?

```sh
docker exec -it rust-mips64le bash
```
<!-- repo=cake233/rust-mips64le -->

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
    cake233/rust-mips64le \
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
    cake233/rust-mips64le \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-mips64le.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-10-07", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_mips64el_2022-10-07_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b11461cfe8c4acb4fdf9fafc971058efc03ec5f27ffb3e1adddc86b04745ffc6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1715106304

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "216M"
zstd_bytes = 226382453

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221003"
previous_tag = "2022-10-03"
previous_file = "rust_mips64el_2022-10-03_03-08-rootfs.tar.zst"
previous_sha256 = "0d8200def4962aa663319b1506adba1b9933e91fe0d1eb1b79cf589b6bbd7cc2"

current_version = "latest01"
current_date = "20221007"
old_file = "rust_mips64el_2022-09-30_03-09-rootfs.tar.zst"
old_sha256 = "fcb166d1789d65826cee320c8216283ef1c9c4321d115f5e275f354c4b7fb298"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2022-10-07_03-06-rootfs.tar.zst
# SHA256SUM=b11461cfe8c4acb4fdf9fafc971058efc03ec5f27ffb3e1adddc86b04745ffc6
# BUILD_DATE=20221007
# BUILD_TAG=2022-10-07
# STATUS=completed
# VERSION=latest01
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-07
begin = 2022-10-07 02:52:26.483259006+00:00
start-sync_0 = 02:59:07
start-zstd = 03:00:03
start-sync_1 = 03:05:54
end-sync_1 = 03:06:14
end = 2022-10-07 03:06:14.297113653+00:00

[server]
repo = "cake233/rust-mips64le"

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
ldd = 'ldd (Debian GLIBC 2.35-2) 2.35'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.66.0-nightly (0b84a35c2 2022-10-03)'
rustc = 'rustc 1.66.0-nightly (0ca356586 2022-10-06)'
cc = 'cc (Debian 12.2.0-3) 12.2.0'
cargo_verbose = '''
cargo 1.66.0-nightly (0b84a35c2 2022-10-03)
release: 1.66.0-nightly
commit-hash: 0b84a35c2c7d70df4875a03eb19084b0e7a543ef
commit-date: 2022-10-03
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.66.0-nightly (0ca356586 2022-10-06)
binary: rustc
commit-hash: 0ca356586fed56002b10920fd21ddf6fb12de797
commit-date: 2022-10-06
host: mips64el-unknown-linux-gnuabi64
release: 1.66.0-nightly
LLVM version: 15.0.2
'''
```
