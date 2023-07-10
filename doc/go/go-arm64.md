# go-arm64

## How to run it?

```sh
docker run \
    -it \
    --name go-arm64 \
    cake233/go-arm64
```

## How to exec shell?

```sh
docker exec -it go-arm64 bash
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
    cake233/go-arm64 \
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

## go-arm64.toml

```toml
[main]
name = "go"
tag = ["latest", "2023-07-10"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_arm64_2023-07-10_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c9dcb8d00960b05df6960f59e463377d7902ce07179207871c249ae16a0e7432"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "863M"
tar_bytes = 904205312

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "189M"
zstd_bytes = 197758457

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230626"
previous_tag = "2023-06-26"
previous_file = "go_arm64_2023-06-26_12-10-rootfs.tar.zst"
previous_sha256 = "e3bd53c4d1f32b0641bea0518aa508dba438965481d631ad1615e806b559e52c"

current_version = "latest01"
current_date = "20230710"
old_file = "go_arm64_2023-06-12_12-11-rootfs.tar.zst"
old_sha256 = "6ea73d505e10ab4d75fb866cb23d9b64b1503ac01ed6699b3fa667d0aa35be0b"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go_arm64_2023-07-10_12-10-rootfs.tar.zst
# SHA256SUM=c9dcb8d00960b05df6960f59e463377d7902ce07179207871c249ae16a0e7432
# BUILD_DATE=20230710
# BUILD_TAG=2023-07-10
# STATUS=completed
# VERSION=latest01
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-10
begin = 2023-07-10 12:02:39.930997577+00:00
start-sync_0 = 12:05:18
start-zstd = 12:05:36
start-sync_1 = 12:10:28
end-sync_1 = 12:10:47
end = 2023-07-10 12:10:47.732092256+00:00

[server]
repo = "cake233/go-arm64"

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
PATH = "/go/bin:/usr/local/go/bin${PATH:+:${PATH}}"
GOPATH = "/go"

[version]
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
go = 'go version go1.20.5 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.20.5'

[other]
workdir = "/go"
```
