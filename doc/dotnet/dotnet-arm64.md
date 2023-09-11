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
tag = ["latest", "2023-09-11", ".NET", "dotnet-sdk"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "dotnet_arm64_2023-09-11_12-48.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3559a455f3ae69c972bc8f14ab3d7c296a33a20d54940a0d2798ab245644e284"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1890427904

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "418M"
zstd_bytes = 437286021

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230828"
previous_tag = "2023-08-28"
previous_file = "dotnet_arm64_2023-08-28_12-33-rootfs.tar.zst"
previous_sha256 = "8557c9ad0ed775fc024228c3d047d1549a5044897db3a6d1163683a1ae6e3233"

current_version = "latest02"
current_date = "20230911"
old_file = "dotnet_arm64_2023-08-14_12-34-rootfs.tar.zst"
old_sha256 = "450f4c07a949c4f1c5f9521d66420d08a061d677e3f4446b5ad149efaa8754d7"
# edition 2021
# DISTRO_NAME=dotnet_arm64
# ROOTFS_FILE=dotnet_arm64_2023-09-11_12-48-rootfs.tar.zst
# SHA256SUM=3559a455f3ae69c972bc8f14ab3d7c296a33a20d54940a0d2798ab245644e284
# BUILD_DATE=20230911
# BUILD_TAG=2023-09-11
# STATUS=completed
# VERSION=latest02
# END_TIME=12:48

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-11
begin = 2023-09-11 12:02:41.613728332+00:00
start-sync_0 = 12:34:21
start-zstd = 12:35:24
start-sync_1 = 12:47:32
end-sync_1 = 12:48:13
end = 2023-09-11 12:48:13.798720625+00:00

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
git = 'git version 2.42.0'
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
