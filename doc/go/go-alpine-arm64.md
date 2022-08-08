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
tag = ["alpine", "2022-08-08", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_arm64_2022-08-08_12-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "804e8339d8b653c05dc194471d4a016766cf4509fd42579d93c4e2f67fbce755"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "357M"
tar_bytes = 373307904

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "82M"
zstd_bytes = 85649681

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220711"
previous_tag = "2022-07-11"
previous_file = "go-musl_arm64_2022-07-11_12-06-rootfs.tar.zst"
previous_sha256 = "9b34c4b5fa333cc81f1a99dc84ac2e09dc7bfa5fbb0ff5e84eb7cd5522a874ff"

current_version = "latest01"
current_date = "20220808"
old_file = "go-musl_arm64_2022-06-27_12-06-rootfs.tar.zst"
old_sha256 = "683772404b6538e0190390490b1ed6ac4be393d06e1a241b78c063ef91dd356a"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go-musl_arm64_2022-08-08_12-07-rootfs.tar.zst
# SHA256SUM=804e8339d8b653c05dc194471d4a016766cf4509fd42579d93c4e2f67fbce755
# BUILD_DATE=20220808
# BUILD_TAG=2022-08-08
# STATUS=completed
# VERSION=latest01
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-08
begin = 2022-08-08 12:02:25.995510402+00:00
start-sync_0 = 12:03:27
start-zstd = 12:03:41
start-sync_1 = 12:06:57
end-sync_1 = 12:07:12
end = 2022-08-08 12:07:12.071788713+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.3'
go = 'go version go1.19 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.19'

[other]
workdir = "/go"
```
