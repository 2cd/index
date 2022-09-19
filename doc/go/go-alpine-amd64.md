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
tag = ["alpine", "2022-09-19", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_amd64_2022-09-19_12-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9f9d07ff30efe3713fc2bec9c90d6a44e42283bb90d4796fb353edb79b86dbbc"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "361M"
tar_bytes = 377784320

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "86M"
zstd_bytes = 89347885

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220905"
previous_tag = "2022-09-05"
previous_file = "go-musl_amd64_2022-09-05_12-07-rootfs.tar.zst"
previous_sha256 = "b75ae5551ee4e1f23f6afa5ece79532b6a53f08ca70c02c55ec3e82f89bb0066"

current_version = "latest01"
current_date = "20220919"
old_file = "go-musl_amd64_2022-08-22_12-07-rootfs.tar.zst"
old_sha256 = "aa571d6a67e6b1f9e70686d61aede92d0446e4ff8102e9a86f0859787c48ca47"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go-musl_amd64_2022-09-19_12-07-rootfs.tar.zst
# SHA256SUM=9f9d07ff30efe3713fc2bec9c90d6a44e42283bb90d4796fb353edb79b86dbbc
# BUILD_DATE=20220919
# BUILD_TAG=2022-09-19
# STATUS=completed
# VERSION=latest01
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-19
begin = 2022-09-19 12:02:27.552500970+00:00
start-sync_0 = 12:03:39
start-zstd = 12:03:52
start-sync_1 = 12:07:04
end-sync_1 = 12:07:17
end = 2022-09-19 12:07:17.523006410+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.3'
go = 'go version go1.19.1 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.19.1'

[other]
workdir = "/go"
```
