# Rebuild and repair notes

## Changes made
- Updated `.github/workflows/build.yml` to install the public Theos iOS SDK collection. The Makefile targets `iphone:clang:latest:14.0`, so the SDK collection is required for a reproducible CI build.
- Checked the `AflatoonMubdi_FILES` list: every source file named by the Makefile is present.
- Checked quoted local `#include` dependencies: no missing project-local headers were found.
- Corrected documentation that referred to a bundled `MARCO-FREEVPN.conf`. No provider VPN profile or private key is included in this archive; supply a fresh provider-issued profile yourself.
- Clarified the GitHub Actions artifact naming/build process.

## Build limitation
This environment is not macOS and does not contain Theos plus an Apple iOS SDK, so an actual iOS dylib compile, link, signing, or device test could not be performed here. Run the GitHub Actions workflow on GitHub to verify the real build. The WireGuard host app and Packet Tunnel extension are separate Xcode targets and are not built by this Theos Makefile.
