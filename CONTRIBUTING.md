# Contributing

RISE is proprietary software. Do not submit code, patches, or other material for inclusion unless you have obtained prior written permission from the copyright holder. Opening an issue or pull request does not grant permission to use, reproduce, modify, or distribute the Software.

Bug reports and feature requests may be submitted through GitHub. Do not include real credentials, license keys, personal data, or machine-specific logs.

## Authorized contributions

If you have written authorization to contribute:

- Keep changes focused and explain user-visible behavior, limitations, and rollback behavior.
- Do not add tweaks that disable security protections or essential Windows services.
- Back up original settings before writing them and provide a clear restore path.
- Do not present unavailable FPS, GPU, ping, or performance values as measurements.
- Do not include real credentials, license keys, personal data, or machine-specific logs.

## Verification

On Windows with the .NET 8 SDK:

```powershell
dotnet build RISE.csproj -c Release
```

For authorized changes, include a concise description, affected areas, and the verification you ran. Update the README when changing user-visible functionality or known limitations.
