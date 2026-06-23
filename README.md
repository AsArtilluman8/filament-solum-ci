# filament-solum-ci

Tiny CI wrapper for a Filament Android build proof for SOLUM.

This repository does not vendor or upload Filament source. The workflow checks out
`google/filament` at tag `v1.71.4` inside GitHub Actions, then attempts a minimal
Android `arm64-v8a` release build route.

## Goal

- prove that Filament `v1.71.4` can be built on GitHub-hosted Linux runners;
- target Android `arm64-v8a` only;
- collect logs even when the build fails;
- upload any produced Android AARs, native `.so` files, and host `matc` if they exist.

Desired outputs, when available:

- `filament-android` AAR
- `gltfio-android` AAR
- `filament-utils-android` AAR
- `filamat-android` AAR
- Android `arm64-v8a` shared libraries
- host `matc`

The workflow is intentionally conservative: it reports the exact route and logs. It
does not claim the Filament fork is ready until GitHub Actions produces artifacts.
