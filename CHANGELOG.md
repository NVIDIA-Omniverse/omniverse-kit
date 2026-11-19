# Changelog

<a id="early-access-2"></a>

## Early Access 2 - 2026-11-18

EA2 expands the developer preview with physics, live collaboration, Linux ARM64,
and updated OV Libraries. This release is for evaluation and feedback; it is not
a production migration target.

### Added

- Physics simulation through ovphysx on Windows/Linux x86_64, disabled by default.
- Live Session integration through ovlive for collaborative editing.
- Linux ARM64 SDK and kernel packages for evaluation on DGX Spark, alongside Windows and Linux x86_64.
- Optional ovrtx loading for applications that only need stage operations without rendering.
  Refer to [Renderer Selection](README.md#renderer-selection).

### Changed

- Library versions in this release: ovstage 0.4, ovrtx 0.7, ovui 0.3.1, ovphysx 0.8,
  and ovlive 0.2.0. Refer to [Built on OV Libraries](README.md#built-on-ov-libraries).
- Scene-loading and runtime performance improvements. Full performance parity
  with Kit 110.4 has not been reached.
- OmniGraph compatibility fixes and extension integration updates. These do not
  imply complete extension or workflow parity with Kit 110.4.

- The EA1 multi-GPU flickering restriction no longer applies.
- The EA1 spatial-audio limitation is narrowed to deleted or deactivated
  listener tracking; refer to [Additional Known Issues](README.md#additional-known-issues).

### Known Issues

- The physics authoring UI extension (`omni.kit.physics.authoring`) is not included.
  Physics simulation is unavailable on ARM64 and disabled by default on x86_64; refer to [Physics Limitations](README.md#physics-limitations)
  for activation and runtime limitations.
- Live synchronization does not visualize other participants in the viewport.
- Linux ARM64 has [extension limitations](README.md#linux-arm64-limitations).
  The asset converter has partial ARM support; FBX is unavailable.
- OCIO color management is not available through the default EA2 settings.
- Content loading, first-frame latency, and timeline playback can be slower than Kit 110.4.
- Viewport FPS can be lower than Kit 110.4 while moving the camera, making scene navigation less smooth.
- OmniGraph GPU, copy, retype, bundle, and scene workloads can still be slower than Kit 110.4.
- First-launch shader compilation can take several minutes, with a blank window or viewport during initialization.
- Additional viewport windows can cause crashes on Windows or Linux.

Review [Known Issues and Compatibility Changes](README.md#known-issues-and-compatibility-changes)
before testing your application or extensions. Packages are listed in
[Downloads](README.md#downloads).

<a id="early-access-1"></a>

## Early Access 1 - 2026-10-16

The first release of NVIDIA Omniverse Kit on OV Libraries is a developer preview
for exploring the new architecture, evaluating applications and extensions, and
providing feedback.

### Added

- Architecture built on ovstage, ovrtx, and ovui. Refer to [Built on OV Libraries](https://github.com/NVIDIA-Omniverse/omniverse-kit/blob/3cae0fb0a263db0dd30aa4a31c362b53d2a4d1fa/README.md#built-on-ov-libraries).
- Kit Base Editor for Windows and Linux. Refer to [Applications](https://github.com/NVIDIA-Omniverse/omniverse-kit/blob/3cae0fb0a263db0dd30aa4a31c362b53d2a4d1fa/README.md#applications).
- SDK with bundled Kit App Template tooling. Refer to [Create a Project from a Template](https://github.com/NVIDIA-Omniverse/omniverse-kit/blob/3cae0fb0a263db0dd30aa4a31c362b53d2a4d1fa/README.md#create-a-project-from-a-template).

### Deprecated

- Hydra. Refer to [Changes from Kit 110.x](https://github.com/NVIDIA-Omniverse/omniverse-kit/blob/3cae0fb0a263db0dd30aa4a31c362b53d2a4d1fa/README.md#changes-from-kit-110x).
- Seven extensions remain available with deprecation warnings. Refer to [Deprecated Extensions](https://github.com/NVIDIA-Omniverse/omniverse-kit/blob/3cae0fb0a263db0dd30aa4a31c362b53d2a4d1fa/README.md#deprecated-extensions).

### Removed

- Fabric from Kit-facing APIs and extension workflows. Refer to [Changes from Kit 110.x](https://github.com/NVIDIA-Omniverse/omniverse-kit/blob/3cae0fb0a263db0dd30aa4a31c362b53d2a4d1fa/README.md#changes-from-kit-110x).
- 50 extensions compared with Kit 110.x. Refer to [Removed Extensions](https://github.com/NVIDIA-Omniverse/omniverse-kit/blob/3cae0fb0a263db0dd30aa4a31c362b53d2a4d1fa/README.md#removed-extensions).

### Known Issues

- **Physics:** Physics is disabled in Early Access 1. Integration with ovphysx is planned for Early Access 2.
- **OmniGraph performance:** Some OmniGraph workflows have known performance issues. Improvements are planned for a future release.
- **Content loading:** Content loading is slower than in Kit 110.4. Improvements to loading performance are planned across upcoming releases.
- **First launch:** Shader compilation can take several minutes, and the window or viewport may remain blank during initialization. Refer to [First Launch and Logs](https://github.com/NVIDIA-Omniverse/omniverse-kit/blob/3cae0fb0a263db0dd30aa4a31c362b53d2a4d1fa/README.md#first-launch-and-logs).

For the EA1-specific known issues and extension availability changes, refer to
[the archived EA1 README](https://github.com/NVIDIA-Omniverse/omniverse-kit/blob/3cae0fb0a263db0dd30aa4a31c362b53d2a4d1fa/README.md#known-issues-and-compatibility-changes).

For setup instructions, refer to [Getting Started](https://github.com/NVIDIA-Omniverse/omniverse-kit/blob/3cae0fb0a263db0dd30aa4a31c362b53d2a4d1fa/README.md#getting-started).
