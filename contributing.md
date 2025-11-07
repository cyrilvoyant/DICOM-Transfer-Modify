# Contributing to DICOM-Transfer-Modify

Thanks for your interest! Quick guidelines:

1. Open an issue before starting large changes.
2. Create a descriptive branch: `feature/xyz` or `fix/typo`.
3. Keep commits focused and with clear messages.
4. Open a Pull Request against `main` and explain the change.

DICOM & binaries rules
- Never commit real patient DICOM files. Use anonymized example data only.
- If you add compiled binaries or external tools, include SHA256 checksums and build instructions.
- Prefer providing source and build steps instead of distributing executables.

A linter will validate Markdown/HTML on PRs.
