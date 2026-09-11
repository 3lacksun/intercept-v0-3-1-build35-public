# INTERCEPT v0.3.1 Build 35 — Android acceptance transport

Public GitHub Actions transport for INTERCEPT Build 35. This repository is not an alternative application source baseline.

## Authoritative source identity

- Archive: `INTERCEPT_V0_3_1_BUILD35_AUTHORITATIVE_RECOVERED_COMPILE_FIXED_HANDOVER_11092026143847.zip`
- SHA-256: `699b17ac3721dfe91da048bab0568b06408ff63178f9f0d8237d971e03b38756`
- Application ID: `com.nexarenew.drstonecommand`
- Version: `0.3.1` / versionCode `35`
- minSdk: `26`
- targetSdk: `36`
- Label: `INTERCEPT`

## Required source transport

The exact authoritative archive is base64-split into zero-padded files under `payload/b64chunk_*`. The acceptance workflow reconstructs `/tmp/src.zip` and rejects it unless its SHA-256 matches the pin above.

Emulator instrumentation is not part of this transport run; unit test, compile, lint, assemble and APK forensics are.

## Acceptance gates

1. Exact source SHA-256 verification and ZIP integrity.
2. `testDebugUnitTest`.
3. `:app:compileDebugKotlin`.
4. `lintDebug`.
5. `assembleDebug`.
6. APK package/version/SDK/label checks, zipalign, signature verification and SHA-256.
7. Evidence and APK artifact upload.

No unexecuted gate is to be represented as PASS.
