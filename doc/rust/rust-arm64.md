# rust-arm64

## How to run it?

```sh
docker run \
    -it \
    --name rust-arm64 \
    cake233/rust-arm64
```

## How to exec shell?

```sh
docker exec -it rust-arm64 bash
```
<!-- repo=cake233/rust-arm64 -->

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
    cake233/rust-arm64 \
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
    cake233/rust-arm64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-arm64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-12-02", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2022-12-02_10-22.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "533ef6af19808a66982a71a2066190f88b4602bebbb088e0d358e385917faba1"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1878244352

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "246M"
zstd_bytes = 257212326

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221128"
previous_tag = "2022-11-28"
previous_file = "rust_arm64_2022-11-28_03-05-rootfs.tar.zst"
previous_sha256 = "f42acb738cf818d88f059abc49713196b0225ba9e0fb7b3ad30601120f84bfa9"

current_version = "latest01"
current_date = "20221202"
old_file = "rust_arm64_2022-11-25_03-05-rootfs.tar.zst"
old_sha256 = "751064353c36d8bdbb93da19c93318980d548d85c4a3d39eb445f3611611956f"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2022-12-02_10-22-rootfs.tar.zst
# SHA256SUM=533ef6af19808a66982a71a2066190f88b4602bebbb088e0d358e385917faba1
# BUILD_DATE=20221202
# BUILD_TAG=2022-12-02
# STATUS=completed
# VERSION=latest01
# END_TIME=10:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-02
begin = 2022-12-02 10:06:46.906770875+00:00
start-sync_0 = 10:14:08
start-zstd = 10:15:30
start-sync_1 = 10:22:22
end-sync_1 = 10:22:47
end = 2022-12-02 10:22:47.565769859+00:00

[server]
repo = "cake233/rust-arm64"

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
ldd = 'ldd (Debian GLIBC 2.36-6) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.67.0-nightly (e027c4b5d 2022-11-25)'
rustc = 'rustc 1.67.0-nightly (c090c6880 2022-12-01)'
cc = 'cc (Debian 12.2.0-9) 12.2.0'
cargo_verbose = '''
cargo 1.67.0-nightly (e027c4b5d 2022-11-25)
release: 1.67.0-nightly
commit-hash: e027c4b5d25af2119b1956fac42863b9b3242744
commit-date: 2022-11-25
host: aarch64-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.67.0-nightly (c090c6880 2022-12-01)
binary: rustc
commit-hash: c090c6880c0183ba248bde4a16e29ba29ac4fbba
commit-date: 2022-12-01
host: aarch64-unknown-linux-gnu
release: 1.67.0-nightly
LLVM version: 15.0.4
'''
```
