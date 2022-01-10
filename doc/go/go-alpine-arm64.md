# go-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name go-alpine-arm64 \
    cake233/go-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it go-alpine-arm64 bash
```

## example

```sh
docker run \
    -t \
    --rm \
    -v "$PWD"/go-project:/app \
    -w /app \
    -e GOOS=linux \
    -e CGO_ENABLED=0 \
    cake233/go-alpine-arm64 \
    go build -trimpath --ldflags "-s -w -buildid=" -v -o main.bin
```

## readme.go
```go
// go run readme.go
package main

import "fmt"

func main() {
	var (
		country, proxy_site string
	)

	country = "China"
	proxy_site = "https://goproxy.cn"
	fmt.Printf("If you live in\x1b[%dm %v. \x1b[0m\n", 32, country)
	fmt.Printf("Then you can run the following\x1b[%dm commands. \x1b[0m\n", 31)

	fmt.Println("go env -w GO111MODULE=on")
	fmt.Printf("go env -w GOPROXY=%v,direct\n", proxy_site)
}
```

## go-alpine-arm64.toml

```toml
[main]
name = "go"
tag = ["alpine", "2022-01-10", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "go-musl_arm64_2022-01-10_12-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "0d9b9e486156faf39002cf73bf3003820f6bcdb89caa56b77a56b0fb4fa29ea1"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "333M"
tar_bytes = 348177920

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "81M"
zstd_bytes = 84575013

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211227"
previous_tag = "2021-12-27"
previous_file = "go-musl_arm64_2021-12-27_12-05-rootfs.tar.zst"
previous_sha256 = "35bd12f8c487c6a79ec38aa23869d6de09d92460ba1598a15e59c37fa92da769"

current_version = "latest02"
current_date = "20220110"
old_file = "go-musl_arm64_2021-12-16_08-26-rootfs.tar.zst"
old_sha256 = "ce2a34f7f35677cc8b86aaabf0a667f11de19af748b84d6e11301e2daaa542cb"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go-musl_arm64_2022-01-10_12-05-rootfs.tar.zst
# SHA256SUM=0d9b9e486156faf39002cf73bf3003820f6bcdb89caa56b77a56b0fb4fa29ea1
# BUILD_DATE=20220110
# BUILD_TAG=2022-01-10
# STATUS=completed
# VERSION=latest02
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-10
begin = 2022-01-10 12:02:28.746906073+00:00
start-sync_0 = 12:03:22
start-zstd = 12:03:32
start-sync_1 = 12:05:01
end-sync_1 = 12:05:11
end = 2022-01-10 12:05:11.542957355+00:00

[server]
repo = "cake233/go-alpine-arm64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
previous = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "C.UTF-8"
PATH = "/go/bin:/usr/local/go/bin${PATH:+:${PATH}}"
GOPATH = "/go"

[version]
ldd = 'musl libc (aarch64) Version 1.2.2'
go = 'go version go1.18beta1 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.18beta1'

[other]
workdir = "/go"
```
