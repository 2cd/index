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
tag = ["alpine", "2022-03-01", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "go-musl_amd64_2022-03-01_18-56.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "ec94406973ff607996c6a08630a8dc728d93c36a98254ace16cb532f22452322"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "337M"
tar_bytes = 352946688

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "85M"
zstd_bytes = 88857529

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220207"
previous_tag = "2022-02-07"
previous_file = "go-musl_amd64_2022-02-07_12-04-rootfs.tar.zst"
previous_sha256 = "bbd096976e87397fc3da5bb6273c9951ae710cc89fbbfe3aafcde753c668986a"

current_version = "latest01"
current_date = "20220301"
old_file = "go-musl_amd64_2022-01-24_12-05-rootfs.tar.zst"
old_sha256 = "17853d317e950134c4b7742622126807ece42ef90e661c8b4b29e7878c8a6fd5"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go-musl_amd64_2022-03-01_18-56-rootfs.tar.zst
# SHA256SUM=ec94406973ff607996c6a08630a8dc728d93c36a98254ace16cb532f22452322
# BUILD_DATE=20220301
# BUILD_TAG=2022-03-01
# STATUS=completed
# VERSION=latest01
# END_TIME=18:56

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-01
begin = 2022-03-01 18:54:25.838931064+00:00
start-sync_0 = 18:54:45
start-zstd = 18:54:57
start-sync_1 = 18:56:24
end-sync_1 = 18:56:36
end = 2022-03-01 18:56:36.926505669+00:00

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
go = 'go version go1.18rc1 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.18rc1'

[other]
workdir = "/go"
```
