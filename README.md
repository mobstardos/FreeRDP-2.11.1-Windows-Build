# FreeRDP 2.11.1 — Windows Build (x64)

Prebuilt **FreeRDP 2.11.1** binaries for Windows, built from source with MSVC.

## What's inside

- `wfreerdp.exe` — RDP client (GUI)
- `wfreerdp-server.exe` — RDP server / shadow
- `freerdp-shadow-cli.exe` — shadow session tool
- `freerdp-proxy.exe` — RDP proxy
- `sfreerdp-server.exe` — sample server
- Channel plugins (`*client.dll`), core libs, bundled **OpenSSL 1.1.1** and **MSVC 143 CRT**

## Download

Grab the prebuilt archive from the
[Releases](https://github.com/mobstardos/FreeRDP-2.11.1-Windows-Build/releases) page:
`FreeRDP-2.11.1-win64.zip`. Just unzip and run — no installer needed.

## Usage

```
wfreerdp.exe /v:host:3389 /u:user /p:password
```

Use the included `connect.bat`:

```
connect.bat 192.168.1.100:3389 JohnDoe P@ssw0rd
```

Double-clicking a `.rdp` file also launches `wfreerdp.exe`.

## Build details

- CMake 3.31 + Visual Studio 2022 Build Tools (MSVC 14.44), Windows SDK 10.0.26100
- `BUILD_SHARED_LIBS=ON`, `BUILTIN_CHANNELS=OFF`, SSE2/NEON disabled
- OpenSSL from the bundled PostgreSQL distribution
- Targets Windows 7–11 (x64)

> Note: the default build targets Windows 7+. For Windows XP a separate
> `WINXP` toolchain (v141_xp + Windows SDK 7.1A) is required.
