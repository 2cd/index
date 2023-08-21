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
tag = ["latest", "2023-08-21"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_arm64_2023-08-21_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8fdbbe1e3b81a855eef93d4c3e644cbeed72a3e6793dddf8a576afe788f3b71a"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "836M"
tar_bytes = 875772928

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "159M"
zstd_bytes = 166501974

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230807"
previous_tag = "2023-08-07"
previous_file = "go_arm64_2023-08-07_12-11-rootfs.tar.zst"
previous_sha256 = "556a664954b77f7493ebd74872b02a206b0224cd346eda721b99382052c846bb"

current_version = "latest02"
current_date = "20230821"
old_file = "go_arm64_2023-07-24_12-10-rootfs.tar.zst"
old_sha256 = "83f561528d6b0dce752fb5d8aacfe0b50f501beabcae08cf6c5b5f5a59a0f1dd"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go_arm64_2023-08-21_12-10-rootfs.tar.zst
# SHA256SUM=8fdbbe1e3b81a855eef93d4c3e644cbeed72a3e6793dddf8a576afe788f3b71a
# BUILD_DATE=20230821
# BUILD_TAG=2023-08-21
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-21
begin = 2023-08-21 12:02:43.270067742+00:00
start-sync_0 = 12:05:17
start-zstd = 12:05:36
start-sync_1 = 12:10:23
end-sync_1 = 12:10:44
end = 2023-08-21 12:10:44.108235083+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u1) 2.36'
go = 'go version go1.21.0 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.21.0'

[other]
workdir = "/go"
```
