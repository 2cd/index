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
tag = ["latest", "2023-10-23", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-10-23_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "75c709cd0ae31cd43e5fe641ece9dbbaf2946d7668c6b76035a423f5b317dad0"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1675612160

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "220M"
zstd_bytes = 229941956

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231020"
previous_tag = "2023-10-20"
previous_file = "rust_armhf_2023-10-20_03-07-rootfs.tar.zst"
previous_sha256 = "07df5b937a6cb6ad0e08b3c54aae92b1aa24d28b56e4cdd1f393448ed5bfc5df"

current_version = "latest02"
current_date = "20231023"
old_file = "rust_armhf_2023-10-16_03-04-rootfs.tar.zst"
old_sha256 = "7f68c3b64c7ccda4bbba9b869fdd5a8ab502e531dacdf94a5b62f99a3267d24d"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-10-23_03-05-rootfs.tar.zst
# SHA256SUM=75c709cd0ae31cd43e5fe641ece9dbbaf2946d7668c6b76035a423f5b317dad0
# BUILD_DATE=20231023
# BUILD_TAG=2023-10-23
# STATUS=completed
# VERSION=latest02
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-23
begin = 2023-10-23 02:52:36.408872464+00:00
start-sync_0 = 02:59:13
start-zstd = 03:00:15
start-sync_1 = 03:05:05
end-sync_1 = 03:05:30
end = 2023-10-23 03:05:30.283540070+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.75.0-nightly (8eb8acbb1 2023-10-17)'
rustc = 'rustc 1.75.0-nightly (1c05d50c8 2023-10-21)'
cc = 'cc (Debian 13.2.0-5) 13.2.0'
cargo_verbose = '''
cargo 1.75.0-nightly (8eb8acbb1 2023-10-17)
release: 1.75.0-nightly
commit-hash: 8eb8acbb116e7923ea2ce33a50109933ed5ab375
commit-date: 2023-10-17
host: armv7-unknown-linux-gnueabihf
libgit2: 1.7.1 (sys:0.18.1 vendored)
libcurl: 8.4.0-DEV (sys:0.4.68+curl-8.4.0 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.75.0-nightly (1c05d50c8 2023-10-21)
binary: rustc
commit-hash: 1c05d50c8403c56d9a8b6fb871f15aaa26fb5d07
commit-date: 2023-10-21
host: armv7-unknown-linux-gnueabihf
release: 1.75.0-nightly
LLVM version: 17.0.3
'''
```
