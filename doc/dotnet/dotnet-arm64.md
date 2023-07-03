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
tag = ["latest", "2023-07-03", ".NET", "dotnet-sdk"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "dotnet_arm64_2023-07-03_12-33.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a8585143f042a81391e6e6005693b1a11f05f2de5c2f485a675c430554ba9d47"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1852149248

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "408M"
zstd_bytes = 427692066

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230605"
previous_tag = "2023-06-05"
previous_file = "dotnet_arm64_2023-06-05_12-31-rootfs.tar.zst"
previous_sha256 = "3c34724fb79f4d09e6ecf0cc46aecee83c6ddcdd6b969fc7624abfbd56b73945"

current_version = "latest01"
current_date = "20230703"
old_file = "dotnet_arm64_2023-05-22_12-33-rootfs.tar.zst"
old_sha256 = "1c36ee7b2d4eeac0f11c74ac90266c9e8e1c2a761241cdda65791b148cb9ad70"
# edition 2021
# DISTRO_NAME=dotnet_arm64
# ROOTFS_FILE=dotnet_arm64_2023-07-03_12-33-rootfs.tar.zst
# SHA256SUM=a8585143f042a81391e6e6005693b1a11f05f2de5c2f485a675c430554ba9d47
# BUILD_DATE=20230703
# BUILD_TAG=2023-07-03
# STATUS=completed
# VERSION=latest01
# END_TIME=12:33

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-03
begin = 2023-07-03 12:02:37.333688708+00:00
start-sync_0 = 12:20:52
start-zstd = 12:21:43
start-sync_1 = 12:32:53
end-sync_1 = 12:33:25
end = 2023-07-03 12:33:25.832871990+00:00

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
dotnet = '7.0.305'
powershell = 'PowerShell 7.3.5'
dotnet_info = '''
.NET SDK:
 Version:   7.0.305
 Commit:    98e1b6c381

Runtime Environment:
 OS Name:     archarm
 OS Version:  
 OS Platform: Linux
 RID:         linux-arm64
 Base Path:   /usr/local/dotnet/sdk/7.0.305/

Host:
  Version:      7.0.8
  Architecture: arm64
  Commit:       4b0550942d

.NET SDKs installed:
  7.0.305 [/usr/local/dotnet/sdk]

.NET runtimes installed:
  Microsoft.AspNetCore.App 7.0.8 [/usr/local/dotnet/shared/Microsoft.AspNetCore.App]
  Microsoft.NETCore.App 7.0.8 [/usr/local/dotnet/shared/Microsoft.NETCore.App]

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
