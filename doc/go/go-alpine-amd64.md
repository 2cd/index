# go-alpine-amd64

## How to run it?

```shell
docker run \
    -it \
    --name go-alpine-amd64 \
    cake233/go-alpine-amd64
```

## How to exec shell?

```shell
    docker exec -it go-alpine-amd64 bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/go-project:/app \
    -w /app \
    cake233/go-alpine-amd64 \
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

## go-alpine-amd64.toml

```toml
[main]
name = "go"
tag = ["alpine", "2021-11-29", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "go-musl_amd64_2021-11-29_19-44.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "3d8026eb04c28d23fd4450213130e4c49605248bd7d259ca0c10503abf3379f6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "323M"
tar_bytes = 338341888

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "81M"
zstd_bytes = 83990891

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211129"
last_tag = "2021-11-29"
last_file = "go-musl_amd64_2021-11-29_00-29-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211129"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go-musl_amd64_2021-11-29_19-44-rootfs.tar.zst
# BUILD_DATE=20211129
# BUILD_TAG=2021-11-29
# STATUS=completed
# VERSION=latest02
# END_TIME=19:44

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-29
begin = 2021-11-29 19:41:53.540557648+00:00
start-sync_0 = 19:42:50
start-zstd = 19:43:02
start-sync_1 = 19:44:22
end-sync_1 = 19:44:41
end = 2021-11-29 19:44:41.075085469+00:00

[server]
repo = "cake233/go-alpine-amd64"

[server.node1]
name = "cn"
current = false
last = true
split = false

[server.node2]
name = "us"
current = false
last = true
split = false
part = 12

[server.node3]
name = "global"
current = false
last = true
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
go = 'go version go1.17.3 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.17.3'

[other]
workdir = "/go"
```
