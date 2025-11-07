# DICOM-Transfer-Modify

Project: DICOM-Transfer-Modify — tools and utilities for transferring and modifying DICOM data

Summary
This repository contains tools and resources related to transferring and modifying DICOM files. The archive `Suite.zip` includes the toolset; please verify contents and ensure no protected health information (PHI) is distributed.

Top-level contents
- `Suite.zip` — tool suite archive (check contents before running)
- `LICENSE` — project license
- `README.md` — this file

Quick view / demo
1. Recommended: enable GitHub Pages and serve the `docs/` folder to provide a simple demo page that embeds documentation and links the Suite archive.
2. After adding `docs/index.html`, enable GitHub Pages (Settings → Pages → Source: Branch `main` / folder `/docs`) — demo will appear at `https://cyrilvoyant.github.io/DICOM-Transfer-Modify/`.

Requirements (do this only once)
To use the scripts (for example the `code.bat` batch), you must download and install:
- DCMTK from OFFIS: https://dicom.offis.de/dcmtk.php.en  
- GDCM tools: http://gdcm.sourceforge.net/html/gdcmconv.html

You also need to add the directories that contain the required `.exe` files to your system `PATH`. For details about updating PATH on Windows, see: https://www.java.com/en/download/help/path.html.

Security / data privacy
- Do not commit real patient DICOM files. Always anonymize DICOM data before adding sample files.
- If distributing binaries, add SHA256 checksums and build/source instructions so users can verify the binary integrity.
- Prefer providing source and build steps instead of distributing executables.

How to use the suite (when necessary)
Only follow this methodology if the usual DICOM transfer software (e.g. CD2RTP for ADAC Pinnacle) does not work.

1. Place the images in the `IMAGES` directory.

2. Check if they all have the same size:
   - If YES: they are probably in "Little Endian" (compatible with ADAC-Pinnacle).
   - If NO: they are compressed (JPEG or JP2000) and not directly compatible with ADAC-Pinnacle.

3. To ensure compression type:
   - Open ezDicom (included in the suite folder or available at https://sourceforge.net/projects/ezdicom/).
   - Load one image from the `IMAGES` directory.
   - Show DICOM tags and check tag (0002,0010). If it ends with `1.2.1` then there is no compression; otherwise the images are likely compressed.

4. Edit and read `code.bat`:
   - RIGHT‑CLICK `code.bat` → Modify to inspect the batch script.
   - The script supports four actions:
     - add a `.dcm` extension to images in `IMAGES`,
     - decompress images (normal JPEG or JP2000),
     - modify DICOM attributes,
     - export images for Pinnacle.
   - To deselect an action, add `rem` at the beginning of the corresponding line in the script (Windows batch comment).
   - LEFT‑CLICK `code.bat` (double‑click/execute) to run the chosen actions.

Notes and safety
- Always inspect files before execution, especially when running downloaded executables or batch scripts.
- Consider creating checksums (SHA256) for distributed binaries and include instructions to verify them.
- If you provide source code (e.g., `codesource.zip`), include build instructions so users can rebuild the binary themselves.

Planned improvements in this PR
- Add `docs/index.html` demo page to preview documentation and link Suite.zip.
- Add `CONTRIBUTING.md` with contribution guidelines and binary handling instructions.
- Add a GitHub Actions workflow to lint Markdown/HTML.
- Add a minimal `.gitignore`.

Contributing
Open an issue for any proposed change or bug. See CONTRIBUTING.md (to be added) for contribution steps.

License
See LICENSE in the repository.
