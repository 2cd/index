# go-amd64

## How to run it?

```sh
docker run \
    -it \
    --name go-amd64 \
    cake233/go-amd64
```

## How to exec shell?

```sh
docker exec -it go-amd64 bash
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
    cake233/go-amd64 \
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

## go-amd64.toml

```toml
[main]
name = "go"
tag = ["latest", "2022-07-25"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_amd64_2022-07-25_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "434469dc01ca4e2437dd878739aab82bf6b013bcd695c0401675993626ed84d4"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "968M"
tar_bytes = 1014301696

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "206M"
zstd_bytes = 215774536

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220711"
previous_tag = "2022-07-11"
previous_file = "go_amd64_2022-07-11_12-09-rootfs.tar.zst"
previous_sha256 = "c6ebf87af69617b734a31d2463d7ffcb5bf0476c46f5ccafaee9c4663c2eff61"

current_version = "latest01"
current_date = "20220725"
old_file = "go_amd64_2022-06-27_12-09-rootfs.tar.zst"
old_sha256 = "29b1639787a9707ed3be1236762f07c11459fffd7cf78a7f19c137ccc5035841"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go_amd64_2022-07-25_12-11-rootfs.tar.zst
# SHA256SUM=434469dc01ca4e2437dd878739aab82bf6b013bcd695c0401675993626ed84d4
# BUILD_DATE=20220725
# BUILD_TAG=2022-07-25
# STATUS=completed
# VERSION=latest01
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-25
begin = 2022-07-25 12:02:42.426900665+00:00
start-sync_0 = 12:04:01
start-zstd = 12:04:55
start-sync_1 = 12:11:27
end-sync_1 = 12:11:51
end = 2022-07-25 12:11:51.906883970+00:00

[server]
repo = "cake233/go-amd64"

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
go = 'go version go1.18.4 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.18.4'

[other]
workdir = "/go"
```
