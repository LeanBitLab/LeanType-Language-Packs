# LeanType Language Packs

This repository hosts translated UI language packs for LeanType, an Android keyboard app.

Packs are resource-only APKs (such as `de.apk`) containing localized UI strings. They are never installed as standalone applications.

Translations are maintained in the main LeanType repository under `app/src/main/res/values-*/strings.xml`, not in this repository.

## For Users

### Requirements
- Android 11 or newer.

### Getting a Pack
- Standard flavor: Open Settings > Languages & Layouts > App translation in LeanType to download the language pack for your locale.
- Offline flavor: Download the matching pack APK from the Releases section of this repository and import it via Settings > Languages & Layouts > App translation.

### Compatibility Across Updates
Each language pack is built for a specific LeanType build and is coupled to that build's exact resource structure. Release tags in this repository follow the format `<versionName>-<crc32 of resources.arsc>`. When you update the LeanType app, previously downloaded packs will not match the new build. You must update or re-download the language pack so its release tag matches your updated app build.

## For Maintainers

### Automated Build Workflow
Language pack releases are generated via GitHub Actions:
1. Go to the Actions tab and select the "Build language packs" workflow.
2. Trigger `workflow_dispatch` by entering the LeanType release tag (e.g. `v4.3.7`).
3. The workflow fetches the release APKs (standard and offline), builds packs for every locale with `tools/build_language_pack.py`, and publishes releases tagged by `<versionName>-<crc32>`.

### Local Build Command
To build a pack locally, use the script from the LeanType repository:

```sh
python3 tools/build_language_pack.py --apk <app.apk> --locale de --out-dir packs
```

## License

This project is licensed under the GNU General Public License v3.0 (GPL-3.0), matching LeanType.
