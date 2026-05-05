# VGS Texture Packer

VGS Texture Packer is a Blazor WebAssembly app for building and converting texture assets used in PBR workflows.
It provides a browser-based workspace to generate maps, pack ORM textures, and convert image formats in single-file and batch modes.

## What This Project Does

- Create ORM textures from AO, Roughness, and Metallic/Gloss inputs.
- Process full folders and generate ORMs in batch.
- Generate AO, Roughness, and Metallic maps from diffuse/base textures.
- Convert textures between PNG and WebP for one file or entire folders.
- Use modern browser file system pickers for folder/file selection and output.

## Tech Stack

- .NET 10
- Blazor WebAssembly
- Bootstrap
- Browser File System Access API (where supported)

## Project Structure

- `TexturePacker.slnx`: Solution file.
- `VGS_TexturePacker/`: Main Blazor WebAssembly project.
- `VGS_TexturePacker/Pages/`: UI pages for each workflow.
- `VGS_TexturePacker/wwwroot/index.html`: Main client-side JavaScript image-processing and file handling logic.

## Prerequisites

- .NET SDK 10.0 (or compatible with target framework `net10.0`)
- A Chromium-based browser for best support of folder/file picker APIs

## Run Locally

From the repository root:

```bash
dotnet run --project VGS_TexturePacker/VGS_TexturePacker.csproj
```

Then open the local URL shown in the terminal.

## Main Workflows

1. Generate maps from diffuse textures:
   - Use **Create Maps** for one texture.
   - Use **Create Maps Folder** to process multiple textures.
2. Build ORM textures:
   - Use **Create ORMs by File** for one set of maps.
   - Use **Create ORMs by Folder** to auto-detect grouped maps and process in batch.
3. Export/convert formats:
   - Use **Export by File** for single-image conversion.
   - Use **Export by Folder** for batch conversion.

## Naming Notes

Batch ORM and map workflows rely on suffix-based naming conventions (for example AO, Roughness, Metallic/Gloss variants).
Consistent naming improves automatic grouping and reduces skipped files.

## Browser Compatibility

Some features depend on:

- `showDirectoryPicker`
- `showOpenFilePicker`
- `showSaveFilePicker`

If these APIs are unavailable in the browser, the app reports feature limitations in the UI.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
