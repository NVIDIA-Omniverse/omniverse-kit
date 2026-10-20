# NVIDIA Omniverse Kit on OV Libraries (Early Access)

NVIDIA Omniverse Kit is a framework for building extensible applications and tools
for OpenUSD workflows.

Kit on OV Libraries is in **Early Access** and is provided as a developer preview
to help you explore the new architecture, evaluate your applications and
extensions, and provide feedback.

> [!IMPORTANT]
> This is **early access software**, provided as is for evaluation and use at your
> own risk. Further early access releases will follow, and APIs,
> extension availability, and workflows may change as development continues.

> [!TIP]
> **Use these docs with your coding agent.** For the best experience, give Claude,
> Codex, or your preferred coding agent this README's URL or local file, along with
> what you want to build.
>
> Example prompt: "Use this README and its linked documentation to help me set up
> Kit on OV Libraries and build [project goal]. Account for the
> documented requirements and known issues."

## Built on OV Libraries

Kit on OV Libraries uses ovstage, ovrtx, and ovui for scene data, RTX rendering,
and user interfaces.

| Library | Version | Role and Availability |
| --- | --- | --- |
| [ovstage](https://github.com/NVIDIA-Omniverse/ovstage) | 0.3 | Shared scene data access and management for OpenUSD-based workflows. |
| [ovrtx](https://github.com/NVIDIA-Omniverse/ovrtx) | 0.6 | RTX rendering, visualization, and sensor simulation. |
| [ovui](https://github.com/NVIDIA-Omniverse/ovui) | 0.3 | User interface, widget, and scene interaction capabilities. |
| [ovphysx](https://github.com/NVIDIA-Omniverse/PhysX/tree/main/ovphysx) | — | Physics is disabled in Early Access 1. Integration with ovphysx is planned for Early Access 2. |

These libraries are also available independently of Kit. Follow the links above
for their APIs, examples, installation instructions, and license terms.

### Changes from Kit 110.x

Kit retains its application and extension model while using OV Libraries for core
services. ovstage manages shared OpenUSD scene data, ovrtx provides RTX rendering,
and ovui provides user interface capabilities.

Fabric is removed from Kit-facing APIs and extension workflows, and Hydra is
deprecated. If your extension uses Fabric or Hydra, review its scene data and
rendering integration against the ovstage and ovrtx APIs. Also check its
dependencies against the [extension availability changes](#extension-availability-changes)
before loading it in Kit on OV Libraries.

## Early Access Releases

| Release | Description |
| --- | --- |
| [Early Access 1](CHANGELOG.md#early-access-1) | First release of Kit on OV Libraries for evaluating applications and extensions and providing feedback. |

Early access releases are not officially supported products and do not include
official support.

For Kit 110.4, refer to
[Kit App Template](https://github.com/NVIDIA-Omniverse/kit-app-template).

To use Kit App Template tooling with Kit on OV Libraries, run `new_project.bat`
on Windows or `new_project.sh` on Linux from the Kit SDK. Refer to
[Create a Project from a Template](#create-a-project-from-a-template) for instructions.

## Applications

Kit Base Editor is the application included in this release for Windows and
Linux:

| Application | Use | Windows launcher | Linux launcher |
| --- | --- | --- | --- |
| Kit Base Editor | Edit USD scenes and develop extensions. | `omni.app.editor.base.bat` | `omni.app.editor.base.sh` |

Kit Base Editor runs from the extracted package, so you do not need to build from
source.

## Downloads

Download the **Kit SDK** to run Kit Base Editor or create projects with the bundled
template tooling. It includes the Kit kernel, development tools, and the
extensions needed to run Kit Base Editor. A separate kernel download is not
required.

The **Kit Kernel** is a smaller package containing the core runtime and template
tooling, without the SDK's bundled extension collection. If you download it
separately, extract it into its own folder.

| Package | Windows x86_64 | Linux x86_64 |
| --- | --- | --- |
| Kit SDK | [Download ZIP](https://d4i3qtqj3r0z5.cloudfront.net/kit-sdk%40111.0.0%2Bfeature.windows-x86_64.release.zip) | [Download ZIP](https://d4i3qtqj3r0z5.cloudfront.net/kit-sdk%40111.0.0%2Bfeature.manylinux_2_35_x86_64.release.zip) |
| Kit Kernel | [Download ZIP](https://d4i3qtqj3r0z5.cloudfront.net/kit-kernel%40111.0.0%2Bfeature.windows-x86_64.release.zip) | [Download ZIP](https://d4i3qtqj3r0z5.cloudfront.net/kit-kernel%40111.0.0%2Bfeature.manylinux_2_35_x86_64.release.zip) |

## Getting Started

For general application and extension development practices, refer to the
[Omniverse Kit documentation](https://docs.omniverse.nvidia.com/kit/docs/kit-manual/latest/index.html).
Use this README to set up Kit on OV Libraries and review the
[compatibility changes](#known-issues-and-compatibility-changes).

The extract-and-launch instructions below use the Kit SDK. For development with
its bundled templates, refer to
[Create a Project from a Template](#create-a-project-from-a-template).

### Requirements

- **Operating System**: Windows 10/11 or Linux (Ubuntu 22.04 or newer).

- **GPU:** An NVIDIA GPU with RTX rendering support.

- **NVIDIA graphics driver:** Windows requires **595.97 or later**. Linux
  requires **595.58.03 or later**.

- **Installation folder:** A writable path, such as `C:\OmniverseKit` on Windows
  or `$HOME/OmniverseKit` on Linux. Use a short Windows path to avoid path-length
  limits during extraction.

- **Disk space:** Space for downloaded archives, extracted packages, shader
  caches, and scene assets.

- **Network:** Access to any online asset and material libraries you choose to use.

### Extract and Launch on Windows

1. Download the Windows x86_64 **Kit SDK** ZIP from [Downloads](#downloads).
2. Extract the ZIP archive into an empty folder, such as `C:\OmniverseKit`.
   Keep all extracted files and directories together.
3. Open PowerShell in the extracted SDK folder containing
   `omni.app.editor.base.bat` and run Kit Base Editor:

   ```powershell
   .\omni.app.editor.base.bat
   ```

### Extract and Launch on Linux

Use Bash and `unzip`. For Kit Base Editor, use a desktop session with NVIDIA
graphics support.

1. Download the Linux x86_64 **Kit SDK** ZIP from [Downloads](#downloads).
   Save it as `kit-sdk.zip` and open a terminal in the download directory.
2. Extract the archive on Linux to preserve executable permissions and symbolic
   links. Use an empty destination folder, such as `$HOME/OmniverseKit`:

   ```bash
   unzip kit-sdk.zip -d "$HOME/OmniverseKit"
   ```

3. Keep all extracted files and directories together. Open the extracted SDK
   folder and run Kit Base Editor:

   ```bash
   cd "$HOME/OmniverseKit"
   ./omni.app.editor.base.sh
   ```

### First Launch and Logs

Allow the first launch to finish compiling shaders. This can take several minutes,
and the window or viewport may remain blank during initialization. Keep the
launcher terminal or console open until the application is ready. Subsequent
launches can reuse the shader cache.

Use **File** > **Open** to open a USD scene, or **File** > **New** to create one.
Use **File** > **Save As** to save your work to a writable location.

In Kit Base Editor, open **Window** > **Extensions** to browse and manage the
extensions available in your package.

Kit prints the log file path near the beginning of the terminal or console output
at startup. Include that log when reporting an issue. For more information, refer
to the [Kit logging documentation](https://docs.omniverse.nvidia.com/kit/docs/kit-manual/latest/guide/logging.html).

### Create a Project from a Template

Kit on OV Libraries includes its own copy of the Kit App Template tooling directly
in the [Kit SDK](#downloads). Use the bundled `new_project` script to create
applications and extensions. Open a terminal in the extracted SDK directory
containing that script and run the command for your platform.

On Windows:

```powershell
.\new_project.bat
```

On Linux:

```bash
./new_project.sh
```

Follow the prompts to choose a project folder and template. The generated project
uses your local Kit kernel. Continue in the generated project folder and follow
its README for building and launching your application or extension.

## Known Issues and Compatibility Changes

These notes apply to this release. Compatibility changes are relative to Kit
110.x; the content-loading performance comparison uses Kit 110.4 specifically.
Review these limitations before evaluating an application or extension.

| Area | Current status |
| --- | --- |
| Physics | Physics is disabled in Early Access 1. Integration with ovphysx is planned for Early Access 2. |
| OmniGraph performance | Some OmniGraph workflows have known performance issues. Improvements are planned for a future release. |
| Content loading | Content loading is slower than in Kit 110.4. Improvements to loading performance are planned across upcoming releases. |
| First launch | Shader compilation can take several minutes, and the window or viewport may remain blank during initialization. Refer to [First Launch and Logs](#first-launch-and-logs). |
| Fabric | Removed from Kit-facing APIs and extension workflows in this release. Applications and extensions that use Fabric require changes. For scene data APIs and examples, refer to [ovstage](https://github.com/NVIDIA-Omniverse/ovstage). |
| Hydra | Deprecated in this release. For rendering APIs and examples, refer to the [ovrtx documentation](https://nvidia-omniverse.github.io/ovrtx/). |

### Additional Known Issues

- Multi-GPU rendering can flicker and fail to display the viewport grid. Do not
  use multi-GPU rendering in this release.
- Kit Base Editor is missing the viewport lighting menu. Scenes without lights
  appear black.
- Plugin loading can report `Ignoring plugin … since a plugin with the same name
  is loaded from … omni.runtime.core`.
- Spatial audio does not work.
- Box selection does not select lights.
- Duplicate MDL directories can cause errors. As a workaround, close Kit and move
  `exts/omni.runtime.core/bin/deps/mdl` from the extracted SDK folder to another
  location outside it. Keep the directory so you can restore it later.

### Extension Availability Changes

The following lists describe extension availability changes compared with Kit
110.x. To inspect the extensions in your package, open **Window** > **Extensions**
in Kit Base Editor.

#### Removed Extensions

The following extensions were removed in this release compared with Kit 110.x.
Removal status applies to this release. Future availability is not specified.

| Area | Removed Extensions |
| --- | --- |
| Animation | `omni.anim.graph.bundle`<br>`omni.anim.graph.core`<br>`omni.anim.graph.ui`<br>`omni.anim.motion_path.bundle`<br>`omni.anim.motion_path.core`<br>`omni.anim.motion_path.ui`<br>`omni.anim.time_samples_player`<br>`omni.anim.xform_constraints` |
| CAD Conversion | `omni.kit.converter.cad`<br>`omni.kit.converter.dgn`<br>`omni.kit.converter.dgn_core`<br>`omni.kit.converter.hoops`<br>`omni.kit.converter.hoops_core`<br>`omni.kit.converter.jt`<br>`omni.kit.converter.jt_core`<br>`omni.services.convert.cad` |
| Developer Tools | `omni.kit.client.alias`<br>`omni.kit.command_macro.window`<br>`omni.kit.extensions.widget.dependency_graph`<br>`omni.kit.perf_startup`<br>`omni.kit.property.example`<br>`omni.kit.usd_docs`<br>`omni.kit.window.usddebug`<br>`omni.ui.scene.docs` |
| Layers and Composition | `omni.kit.window.composition`<br>`omni.kit.window.layer_stack` |
| Paint | `omni.paint.brush.scatter`<br>`omni.paint.brush.scripting`<br>`omni.paint.system.bundle`<br>`omni.paint.system.core`<br>`omni.paint.system.ui` |
| Scene Editing Tools | `omni.kit.manipulator.tool.mesh_snap`<br>`omni.tools.array`<br>`omni.tools.distribute`<br>`omni.tools.pivot`<br>`omni.tools.randomizer` |
| Scripting | `omni.kit.scripting` |
| Sequencing | `omni.kit.property.sequence`<br>`omni.kit.sequencer.core`<br>`omni.kit.sequencer.usd`<br>`omni.kit.window.sequencer`<br>`omni.usd.schema.sequence` |
| Stage Recording | `omni.kit.stagerecorder.bundle`<br>`omni.kit.stagerecorder.core`<br>`omni.kit.stagerecorder.ui` |
| Substance | `omni.kit.property.sbsar`<br>`omni.usd.fileformat.sbsar` |
| Warp | `omni.warp`<br>`omni.warp.samples` |
| XR | `omni.kit.xr.cloudxr` |

#### Notes on Alternatives

| Removed Capability | Available Options |
| --- | --- |
| Layer Stack window | Use the Layers window provided by [`omni.kit.widget.layers`](https://docs.omniverse.nvidia.com/kit/docs/omni.kit.widget.layers/1.9.2/Overview.html) to view and edit USD layers. |
| Legacy behavior scripting (`omni.kit.scripting`) | The successor is `omni.behavior.scripting.bundle`, which is not included in the Kit SDK. The Script Editor (`omni.kit.window.script_editor`) remains available for running Python scripts. |
| Legacy Warp wrapper and samples | `omni.warp.core` remains packaged. For standalone use, NVIDIA Warp is available as the [`warp-lang` Python package](https://github.com/NVIDIA/warp). |
| CAD, DGN, HOOPS, and JT import | These importers are not included. Convert CAD content to USD before opening it in Kit. General asset conversion remains available through [`omni.kit.asset_converter`](https://docs.omniverse.nvidia.com/extensions/latest/ext_asset-converter.html) for supported formats such as OBJ, FBX, and glTF. |

#### Deprecated Extensions

The following extensions remain available with deprecation warnings:

- `omni.anim.camera_tool`
- `omni.anim.graph.schema`
- `omni.entity.spawn.bundle`
- `omni.entity.spawn.core`
- `omni.entity.spawn.ui`
- `omni.kit.graph.delegate.neo`
- `omni.kit.graph.editor.example`

## Developing Extensions

### Load a Local Extension

Use Kit Base Editor to evaluate an extension from your local filesystem. From the
SDK folder, add the directory containing your extensions with
`--ext-folder` and enable an extension by its ID with `--enable`.

For example, if your extension manifest is
`C:\MyProject\exts\example.my_extension\config\extension.toml`, run:

```powershell
.\omni.app.editor.base.bat --ext-folder "C:\MyProject\exts" --enable example.my_extension
```

On Linux, the equivalent command for
`$HOME/MyProject/exts/example.my_extension/config/extension.toml` is:

```bash
./omni.app.editor.base.sh --ext-folder "$HOME/MyProject/exts" --enable example.my_extension
```

Replace the example path and extension ID with your own. `--ext-folder` adds a
search location; `--enable` loads the named extension and resolves its
dependencies. Use **Window** > **Extensions** to check its status and the
[application log](#first-launch-and-logs) to diagnose dependency or startup errors.
For general command-line syntax, refer to the
[Kit configuration reference](https://docs.omniverse.nvidia.com/kit/docs/kit-manual/latest/guide/configuring.html).

### Dependencies and API References

The Kit SDK includes the extensions needed to run Kit Base Editor.
For local development, use dependency versions compatible with
your release of Kit on OV Libraries. Extensions built for Kit 110.x may require
changes to their APIs or dependencies.

For the underlying library APIs and examples, refer to
[Built on OV Libraries](#built-on-ov-libraries).

## Feedback and Support

Use [GitHub Issues](https://github.com/NVIDIA-Omniverse/omniverse-kit/issues) to share
feedback, report reproducible bugs, describe compatibility problems, or request
improvements. Include the release version you are using,
the application you launched, operating system, GPU and driver, relevant extension
versions, reproduction steps, and the [application log](#first-launch-and-logs).
The log records component versions that help identify your environment. Feedback
helps guide future updates.

## Related Resources

- [OV Libraries](#built-on-ov-libraries)—use individual libraries
  directly in your own applications.
- [Kit App Template](https://github.com/NVIDIA-Omniverse/kit-app-template)—application
  templates for existing Kit releases.

## Data Collection

Kit collects anonymous usage data to help improve software performance and
diagnostics. For information about the data collected and how NVIDIA uses it,
refer to the [Data Collection FAQ](https://docs.omniverse.nvidia.com/usd/latest/common/data-collection.html).

For technical details, including how to configure or disable telemetry, refer to
the [Omniverse Telemetry documentation](https://docs.omniverse.nvidia.com/kit/docs/carbonite/latest/docs/structuredlog/OmniTelemetry.html#anonymous-data-mode).

## Contributing

This early access release is distributed as binaries and is not source available.
At this time, this project is not open to external contributions.

To report issues or suggest improvements, refer to [Feedback and Support](#feedback-and-support).

## License and Security

This project uses NVIDIA's proprietary license. Refer to [LICENSE](LICENSE) for the
NVIDIA Software License Agreement and included product-specific terms.

Library and dependency licenses are documented in their respective repositories
and packages.

To report a potential security vulnerability, follow [SECURITY.md](SECURITY.md).
Do not report security vulnerabilities through public GitHub issues.
