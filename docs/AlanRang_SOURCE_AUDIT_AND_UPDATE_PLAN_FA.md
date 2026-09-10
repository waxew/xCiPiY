# AlanRang Source Audit & Update Plan

## Source Reviewed

Uploaded source archive:
`AlanRang_v39_43_2_RESERVATION_NOTICE_CANDIDATE4_FIXED2_SOURCE.zip`

Initial structure review:

- Android project source موجود است.
- Native Android resources موجود است.
- Asset/WebView layer موجود است.
- Binary reference files موجود است.
- Candidate verification documents موجود است.

## Comparison With Project Goals

### Existing Candidate Contains

- APK recovery/candidate workflow
- Native Android wrapper structure
- WebView asset based application layer
- Previous candidate verification documents
- Export related resources
- Reservation/Notice candidate history

### Missing Or Requiring Improvement

The following items should be added or hardened in future updates:

- Final locked architecture document
- Complete build history
- Full clean source structure without candidate leftovers
- Final Release signing documentation
- Final APK verification report
- SHA256 release hashes
- Device installation test report

## Engineering Rules For Future Updates

### Build Method

```
Existing APK
    ↓
Extract
    ↓
Asset/WebView Modification
    ↓
Preserve Native Wrapper
    ↓
Repack
    ↓
Sign
    ↓
Install/Test
```

## Forbidden Changes

- Do not remove existing features only to achieve a successful build.
- Do not create a minimal empty APK.
- Do not replace the real project with a demonstration project.
- Do not introduce temporary patches as final solutions.

## Architecture Target

```
WebView Layer
      ↓
JavaScript Logic
      ↓
Canvas/Image Rendering
      ↓
Blob/File
      ↓
Android Bridge
      ↓
Native Save
```

Technical debt to improve:

- Export pipeline reliability
- Bridge error handling
- File verification after save
- Large image handling

## AlanRang Candidate Target

The target version should provide:

- Independent application identity
- New data lifecycle starting from Spring 1405
- Multi-year support (1406, 1407 and future years)
- Stable customer/finance/invoice workflow
- Secure backup and restore
- Maintainable source code

## Current Status

Completed:

- Project goal definition
- Repository documentation
- Architecture review
- Candidate source review

Future updates:

- Import final source archive
- Publish release APK
- Publish signing information
- Complete production validation
