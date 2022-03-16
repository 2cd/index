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
tag = ["alpine", "2022-03-16", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "go-musl_amd64_2022-03-16_07-53.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "59dd1344c649d6f4e5c566e70f834f64aa33fe57f46df45402090c8cb82e1dd7"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "337M"
tar_bytes = 353178624

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "81M"
zstd_bytes = 84556217

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220307"
previous_tag = "2022-03-07"
previous_file = "go-musl_amd64_2022-03-07_12-06-rootfs.tar.zst"
previous_sha256 = "f698a91299a199c9433d32609ec1a4dd0d50712df2e6e1dcf8735eb3afd39557"

current_version = "latest01"
current_date = "20220316"
old_file = "go-musl_amd64_2022-03-01_18-56-rootfs.tar.zst"
old_sha256 = "ec94406973ff607996c6a08630a8dc728d93c36a98254ace16cb532f22452322"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go-musl_amd64_2022-03-16_07-53-rootfs.tar.zst
# SHA256SUM=59dd1344c649d6f4e5c566e70f834f64aa33fe57f46df45402090c8cb82e1dd7
# BUILD_DATE=20220316
# BUILD_TAG=2022-03-16
# STATUS=completed
# VERSION=latest01
# END_TIME=07:53

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-16
begin = 2022-03-16 07:48:41.718578771+00:00
start-sync_0 = 07:49:21
start-zstd = 07:49:33
start-sync_1 = 07:52:51
end-sync_1 = 07:53:04
end = 2022-03-16 07:53:04.474129734+00:00

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
go = 'go version go1.18 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.18'

[other]
workdir = "/go"
```
