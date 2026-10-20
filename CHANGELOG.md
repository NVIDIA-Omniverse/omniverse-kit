# Changelog

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

For the full list of known issues and extension availability changes, refer to
[Known Issues and Compatibility Changes](README.md#known-issues-and-compatibility-changes).

For setup instructions, refer to [Getting Started](README.md#getting-started).
