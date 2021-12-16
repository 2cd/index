# go-alpine-arm64

## How to run it?

```shell
docker run \
    -it \
    --name go-alpine-arm64 \
    cake233/go-alpine-arm64
```

## How to exec shell?

```shell
    docker exec -it go-alpine-arm64 bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/go-project:/app \
    -w /app \
    cake233/go-alpine-arm64 \
    go build -v
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
tag = ["alpine", "2021-12-16", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "go-musl_arm64_2021-12-16_08-26.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "ce2a34f7f35677cc8b86aaabf0a667f11de19af748b84d6e11301e2daaa542cb"

# zstd: [1-22]
zstd-level = 11

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "333M"
tar_bytes = 348177920

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "98M"
zstd_bytes = 102331749

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211213"
previous_tag = "2021-12-13"
previous_file = "go-musl_arm64_2021-12-13_12-04-rootfs.tar.zst"
previous_sha256 = "b934f1dd23c179cdde213ba57c59f4309bca85d6c373b8ef66142a60616b28cf"

current_version = "latest02"
current_date = "20211216"
old_file = "go-musl_arm64_2021-12-08_01-09-rootfs.tar.zst"
old_sha256 = "82b7a17cef63b66dfd5a33c963b2079528a54810ad41c9ac790241b68464266d"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go-musl_arm64_2021-12-16_08-26-rootfs.tar.zst
# SHA256SUM=ce2a34f7f35677cc8b86aaabf0a667f11de19af748b84d6e11301e2daaa542cb
# BUILD_DATE=20211216
# BUILD_TAG=2021-12-16
# STATUS=completed
# VERSION=latest02
# END_TIME=08:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-16
begin = 2021-12-16 08:25:28.527252294+00:00
start-sync_0 = 08:26:13
start-zstd = 08:26:22
start-sync_1 = 08:26:26
end-sync_1 = 08:26:38
end = 2021-12-16 08:26:38.808690576+00:00

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
ldd = ''
go = 'go version go1.18beta1 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.18beta1'

[other]
workdir = "/go"
```
