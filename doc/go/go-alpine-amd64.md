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
tag = ["alpine", "2022-04-19", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "go-musl_amd64_2022-04-19_00-43.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a707f11f6147559977111a4e09c5b96f93313b2abe780c18a4f1dcbc00bff18b"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "337M"
tar_bytes = 353215488

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "81M"
zstd_bytes = 84550956

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220404"
previous_tag = "2022-04-04"
previous_file = "go-musl_amd64_2022-04-04_11-07-rootfs.tar.zst"
previous_sha256 = "e29d0c01b1dc4e64a58535317928d1d20aa141f859741f6a4b23025486467f22"

current_version = "latest02"
current_date = "20220419"
old_file = "go-musl_amd64_2022-03-21_12-06-rootfs.tar.zst"
old_sha256 = "c1fb61c4b10ba9d82a72fa7aa8f84675d43ed75eb35d5cc0898dbdf454c33f4a"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go-musl_amd64_2022-04-19_00-43-rootfs.tar.zst
# SHA256SUM=a707f11f6147559977111a4e09c5b96f93313b2abe780c18a4f1dcbc00bff18b
# BUILD_DATE=20220419
# BUILD_TAG=2022-04-19
# STATUS=completed
# VERSION=latest02
# END_TIME=00:43

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-19
begin = 2022-04-19 00:39:59.516072006+00:00
start-sync_0 = 00:40:25
start-zstd = 00:40:33
start-sync_1 = 00:43:47
end-sync_1 = 00:43:59
end = 2022-04-19 00:43:59.884973273+00:00

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
go = 'go version go1.18.1 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.18.1'

[other]
workdir = "/go"
```
