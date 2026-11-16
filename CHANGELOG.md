# Changelog

<a id="early-access-2"></a>

## Early Access 2 - Unreleased

EA2 expands the developer preview with physics, live collaboration, Linux ARM64,
and updated OV Libraries. This release is for evaluation and feedback; it is not
a production migration target.

### Added

- Physics simulation and basic authoring through ovphysx, replacing EA1's disabled physics.
- Live Session integration through ovlive for collaborative editing.
- Linux ARM64 SDK and kernel packages for evaluation on DGX Spark, alongside Windows and Linux x86_64.
- Optional OVRTX loading for applications that only need stage operations without rendering.

### Changed

- Updated versions of the integrated OV Libraries. Final versions are pending in
  [Built on OV Libraries](README.md#built-on-ov-libraries).
- Scene-loading and runtime performance improvements. Full performance parity
  with Kit 110.4 has not been reached.
- OmniGraph compatibility fixes and extension integration updates. These do not
  imply complete extension or workflow parity with Kit 110.4.

### Known Issues

- Physics simulation and authoring have [documented limitations](README.md#physics-limitations).
- Live synchronization does not visualize other participants in the viewport.
- Linux ARM64 does not include every x86_64 extension, including the asset converter.
- OCIO color management is not available through the default EA2 settings.
- Content loading, startup, and timeline playback can be slower than Kit 110.4.
- Additional viewport windows can cause crashes on Windows or Linux.

Review [Known Issues and Compatibility Changes](README.md#known-issues-and-compatibility-changes)
before testing your application or extensions. Download placeholders are in
[Downloads](README.md#downloads).

<a id="early-access-1"></a>

## Early Access 1 - 2026-10-16

The first release of NVIDIA Omniverse Kit on OV Libraries is a developer preview
for exploring the new architecture, evaluating applications and extensions, and
providing feedback.

### Added

- Architecture built on ovstage, ovrtx, and ovui. Refer to [Built on OV Libraries](README.md#built-on-ov-libraries).
- Kit Base Editor for Windows and Linux. Refer to [Applications](README.md#applications).
- SDK with bundled Kit App Template tooling. Refer to [Create a Project from a Template](README.md#create-a-project-from-a-template).

### Deprecated

- Hydra. Refer to [Changes from Kit 110.x](README.md#changes-from-kit-110x).
- Seven extensions remain available with deprecation warnings. Refer to [Deprecated Extensions](README.md#deprecated-extensions).

### Removed

- Fabric from Kit-facing APIs and extension workflows. Refer to [Changes from Kit 110.x](README.md#changes-from-kit-110x).
- 50 extensions compared with Kit 110.x. Refer to [Removed Extensions](README.md#removed-extensions).

### Known Issues

- **Physics:** Physics is disabled in Early Access 1. Integration with ovphysx is planned for Early Access 2.
- **OmniGraph performance:** Some OmniGraph workflows have known performance issues. Improvements are planned for a future release.
- **Content loading:** Content loading is slower than in Kit 110.4. Improvements to loading performance are planned across upcoming releases.
- **First launch:** Shader compilation can take several minutes, and the window or viewport may remain blank during initialization. Refer to [First Launch and Logs](README.md#first-launch-and-logs).

For the EA1-specific known issues and extension availability changes, refer to
[the archived EA1 README](https://github.com/NVIDIA-Omniverse/omniverse-kit/blob/3cae0fb0a263db0dd30aa4a31c362b53d2a4d1fa/README.md#known-issues-and-compatibility-changes).

For setup instructions, refer to [Getting Started](README.md#getting-started).
