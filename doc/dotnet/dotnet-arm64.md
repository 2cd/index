# dotnet-arm64

## Example

```sh
TMP="/tmp/hello"
mkdir -p "$TMP"

docker run \
    -t \
    --rm \
    -v "$TMP":/app \
    -w /app \
    cake233/dotnet-arm64 \
    dotnet new console -o world

docker run \
    -t \
    --rm \
    -v "$TMP"/world:/app \
    -w /app \
    cake233/dotnet-arm64 \
    dotnet run --verbosity 4
```

## How to exec shell?

```sh
docker run \
    -it \
    --name dotnet-arm64 \
    cake233/dotnet-arm64
```

You can also specify the absolute path to the shell.

```sh
docker exec -it dotnet-arm64 /usr/local/powershell/pwsh
```


## dotnet-arm64.toml

```toml
[main]
name = "dotnet"
tag = ["latest", "2023-08-14", ".NET", "dotnet-sdk"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "dotnet_arm64_2023-08-14_12-34.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "450f4c07a949c4f1c5f9521d66420d08a061d677e3f4446b5ad149efaa8754d7"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1897951744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "418M"
zstd_bytes = 437357184

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230731"
previous_tag = "2023-07-31"
previous_file = "dotnet_arm64_2023-07-31_12-31-rootfs.tar.zst"
previous_sha256 = "f38169b438d9dfd9d8bd23de4c6bf6bb63ba10899e9a5acc394ff8bdcfdb50f3"

current_version = "latest02"
current_date = "20230814"
old_file = "dotnet_arm64_2023-07-17_12-31-rootfs.tar.zst"
old_sha256 = "f050deb3cb8950ad073a934b521ac396cd2e5c615ebb6b96db9ea4d3f25f7e53"
# edition 2021
# DISTRO_NAME=dotnet_arm64
# ROOTFS_FILE=dotnet_arm64_2023-08-14_12-34-rootfs.tar.zst
# SHA256SUM=450f4c07a949c4f1c5f9521d66420d08a061d677e3f4446b5ad149efaa8754d7
# BUILD_DATE=20230814
# BUILD_TAG=2023-08-14
# STATUS=completed
# VERSION=latest02
# END_TIME=12:34

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-14
begin = 2023-08-14 12:02:35.337421222+00:00
start-sync_0 = 12:21:41
start-zstd = 12:22:31
start-sync_1 = 12:33:31
end-sync_1 = 12:34:04
end = 2023-08-14 12:34:04.091694893+00:00

[server]
repo = "cake233/dotnet-arm64"

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
PATH = "/usr/local/powershell:/usr/local/dotnet/bin${PATH:+:${PATH}}"
DOTNET_ROOT = "/usr/local/dotnet"
DOTNET_RUNNING_IN_CONTAINER = true
ASPNETCORE_URLS = ""
DOTNET_GENERATE_ASPNET_CERTIFICATE = false
DOTNET_USE_POLLING_FILE_WATCHER = true
Logging__Console__FormatterName = ""
NUGET_XMLDOC_MODE = "skip"

[version]
ldd = 'ldd (GNU libc) 2.35'
git = 'git version 2.41.0'
dotnet = '7.0.400'
powershell = 'PowerShell 7.3.6'
dotnet_info = '''
.NET SDK:
 Version:   7.0.400
 Commit:    73bf45718d

Runtime Environment:
 OS Name:     archarm
 OS Version:  
 OS Platform: Linux
 RID:         linux-arm64
 Base Path:   /usr/local/dotnet/sdk/7.0.400/

Host:
  Version:      7.0.10
  Architecture: arm64
  Commit:       a6dbb800a4

.NET SDKs installed:
  7.0.400 [/usr/local/dotnet/sdk]

.NET runtimes installed:
  Microsoft.AspNetCore.App 7.0.10 [/usr/local/dotnet/shared/Microsoft.AspNetCore.App]
  Microsoft.NETCore.App 7.0.10 [/usr/local/dotnet/shared/Microsoft.NETCore.App]

Other architectures found:
  None

Environment variables:
  DOTNET_ROOT       [/usr/local/dotnet]

global.json file:
  Not found

Learn more:
  https://aka.ms/dotnet/info

Download .NET:
  https://aka.ms/dotnet/download
'''

[other]
cmd = "/usr/local/powershell/pwsh"
```
