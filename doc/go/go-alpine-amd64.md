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
tag = ["alpine", "2022-05-30", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_amd64_2022-05-30_12-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "08021708d1b5725c820dce90532da30eaac1c2324463e845f40c4eb85931f2c9"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "337M"
tar_bytes = 353176576

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "81M"
zstd_bytes = 84588252

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220516"
previous_tag = "2022-05-16"
previous_file = "go-musl_amd64_2022-05-16_12-06-rootfs.tar.zst"
previous_sha256 = "337b080eb67492bcd4e84551688074a93747e42635d12aa8af973ba7dc521a8f"

current_version = "latest02"
current_date = "20220530"
old_file = "go-musl_amd64_2022-05-02_12-06-rootfs.tar.zst"
old_sha256 = "347a9ed8647623fa86e3bf8b55473527a55a3bc9f4089d7838953bd77f452462"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go-musl_amd64_2022-05-30_12-06-rootfs.tar.zst
# SHA256SUM=08021708d1b5725c820dce90532da30eaac1c2324463e845f40c4eb85931f2c9
# BUILD_DATE=20220530
# BUILD_TAG=2022-05-30
# STATUS=completed
# VERSION=latest02
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-30
begin = 2022-05-30 12:02:41.023024745+00:00
start-sync_0 = 12:03:14
start-zstd = 12:03:23
start-sync_1 = 12:06:23
end-sync_1 = 12:06:33
end = 2022-05-30 12:06:33.232848226+00:00

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
go = 'go version go1.18.2 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.18.2'

[other]
workdir = "/go"
```
