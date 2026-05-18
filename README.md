# Blackhole Webserver for OpenWRT

A lightweight, high-performance Go-based utility designed to capture, log, and mirror HTTP requests. Optimized for OpenWRT routers (ARM64).

## Features
- **Catch-all Routing**: Responds to all requests.
- **Request Mirroring**: Replicates URL paths in `blackhole_root/`.
    - Paths with extensions create empty files.
    - Paths without extensions create directory structures.
- **Logging**: Detailed JSON metadata in `blackhole.log`.
- **Response**: Serves a 1x1 transparent tracking GIF.

## Installation

### Manual (Static Binary)
1. Download or compile the binary for your architecture.
2. Run: `./blackhole-server`

### OpenWRT (APK/IPK)
1. Add this package to your OpenWRT buildroot.
2. Run: `make package/utils/blackhole/compile`
3. Install the resulting package on your router.

## Usage
By default, the server listens on port `8080`.

```bash
# Example requests
curl http://router-ip:8080/path/to/script.js
curl http://router-ip:8080/api/v1/track/
```

Files and directories will be created in `./blackhole_root/` relative to the binary.

## License
MIT
