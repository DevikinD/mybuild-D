# ARM64EC Builds for FEX and DXVK

This repository provides pre-built binaries of [FEX](https://github.com/FEX-Emu/FEX) and [DXVK](https://github.com/doitsujin/dxvk) compiled for **ARM64EC** architecture. These builds are optimized for running x86/x64 applications on ARM64 devices, enabling better compatibility and performance.

## Downloads
Pre-built binaries are available in the [Releases](https://github.com/DevikinD/mybuild-D/releases) section. Simply download and follow the included instructions to get started.

# Installation Instructions

Follow the steps below to install **FEX** and **DXVK** for ARM64EC on your system.

---

## Installing FEX

1. **Download the FEX binaries**:
   - Download the `fex-dlls.tar.xz` file from the [Releases](https://github.com/DevikinD/mybuild-D/releases/tag/FEX-arm64ec) section.

2. **Extract the files**:
   - Extract the `fex-dlls.tar.xz` file to the appropriate Wine directory:
     ```bash
     tar -xvf fex-dlls.tar.xz -C /path/to/wine/lib/aarch64-windows/
     ```
   - Replace `/path/to/wine/lib/aarch64-windows/` with the actual path to your Wine installation's `aarch64-windows` directory.

3. **Verify the extraction**:
   - After extraction, ensure the following files are present in the `aarch64-windows` directory:
     - `libarm64ecfex.dll`
     - `libwow64fex.dll`

---

## Installing DXVK

1. **Download the DXVK binaries**:
   - Download the DXVK `.tar.gz` file from the [Releases](https://github.com/DevikinD/mybuild-D/releases/tag/dxvk-build) section.

2. **Extract the DXVK files**:
   - Extract the `.tar.gz` file to a location of your choice. This will provide the necessary `.dll` files (e.g., `d3d9`, `d3d10core`, `d3d11`, etc.).

3. **Copy the DXVK files to the game directory**:
   - Move or copy the extracted `.dll` files into the game's directory, placing them next to the game's `.exe` file.

4. **Configure Wine to use DXVK**:
   - Open `winecfg`:
     ```bash
     winecfg
     ```
   - Navigate to the **Libraries** tab.
   - In the **New override for library** field, add each DXVK `.dll` file (e.g., `d3d8`, `d3d9`, `d3d10core`, `d3d11`, `dxgi`).
   - For **ARM64EC builds**, set each `.dll` to **"Native"**.
   - For **non-ARM64EC builds**, set each `.dll` to **"Native then Builtin"**.
   - Click **Apply** to save the changes.
