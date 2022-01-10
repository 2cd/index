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
tag = ["alpine", "2022-01-10", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "go-musl_amd64_2022-01-10_12-06.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "33ae0792584b3db71a4574395415ef85b1daa573c1c83e77be35a67b07b81235"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "336M"
tar_bytes = 351834624

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "85M"
zstd_bytes = 88488118

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211227"
previous_tag = "2021-12-27"
previous_file = "go-musl_amd64_2021-12-27_12-06-rootfs.tar.zst"
previous_sha256 = "d3eb254a92d3a7d286fe5e17ffd002b9103b31dacb48f1b3a06494b3e432d170"

current_version = "latest02"
current_date = "20220110"
old_file = "go-musl_amd64_2021-12-16_08-26-rootfs.tar.zst"
old_sha256 = "9c49dd2f07e0d96be5f41e3de739705f865ca91ff742cf1a5ef10149dae32382"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go-musl_amd64_2022-01-10_12-06-rootfs.tar.zst
# SHA256SUM=33ae0792584b3db71a4574395415ef85b1daa573c1c83e77be35a67b07b81235
# BUILD_DATE=20220110
# BUILD_TAG=2022-01-10
# STATUS=completed
# VERSION=latest02
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-10
begin = 2022-01-10 12:02:33.147627843+00:00
start-sync_0 = 12:03:29
start-zstd = 12:03:44
start-sync_1 = 12:05:52
end-sync_1 = 12:06:07
end = 2022-01-10 12:06:07.936575842+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.2'
go = 'go version go1.18beta1 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.18beta1'

[other]
workdir = "/go"
```
