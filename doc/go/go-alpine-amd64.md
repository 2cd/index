# go-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name go-alpine-amd64 \
    cake233/go-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it go-alpine-amd64 bash
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
    cake233/go-alpine-amd64 \
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

## go-alpine-amd64.toml

```toml
[main]
name = "go"
tag = ["alpine", "2023-08-07", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_amd64_2023-08-07_12-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f28c3c010403efa3126356db314cb90de4fe8bb4613c321b6f84c530441ed838"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "268M"
tar_bytes = 280681984

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "73M"
zstd_bytes = 76085676

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230724"
previous_tag = "2023-07-24"
previous_file = "go-musl_amd64_2023-07-24_12-06-rootfs.tar.zst"
previous_sha256 = "2294f233a8598d79bfc76bb4562df35c6083417e054df6e682464dbe0d02747c"

current_version = "latest01"
current_date = "20230807"
old_file = "go-musl_amd64_2023-07-10_12-06-rootfs.tar.zst"
old_sha256 = "fb48670259e74cc5819e229da6095e9b91fc954afcd5b01345e0e8ba6862ef1a"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go-musl_amd64_2023-08-07_12-06-rootfs.tar.zst
# SHA256SUM=f28c3c010403efa3126356db314cb90de4fe8bb4613c321b6f84c530441ed838
# BUILD_DATE=20230807
# BUILD_TAG=2023-08-07
# STATUS=completed
# VERSION=latest01
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-07
begin = 2023-08-07 12:02:41.191640100+00:00
start-sync_0 = 12:03:56
start-zstd = 12:04:05
start-sync_1 = 12:06:43
end-sync_1 = 12:06:53
end = 2023-08-07 12:06:53.726584494+00:00

[server]
repo = "cake233/go-alpine-amd64"

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
LANG = "C.UTF-8"
PATH = "/go/bin:/usr/local/go/bin${PATH:+:${PATH}}"
GOPATH = "/go"

[version]
ldd = 'musl libc (x86_64) Version 1.2.4'
go = 'go version go1.20.7 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.20.7'

[other]
workdir = "/go"
```
