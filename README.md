# LeanType Language Packs

Official translated UI language packs repository for [LeanType Keyboard](https://github.com/LeanBitLab/LeanType).

Packs are resource-only APKs (such as `de.apk`) containing localized UI strings. They are never installed as standalone applications.

Translations are maintained in the main [LeanType repository](https://github.com/LeanBitLab/LeanType) under `app/src/main/res/values-*/strings.xml`, not in this repository.

## 📋 System Requirements

- **Operating System**: Android 11 or newer
- **Host Keyboard**: [LeanType](https://github.com/LeanBitLab/LeanType) English-only `-lite-release.apk` builds (Standard or Offline flavor). The regular APKs, including the F-Droid build, already contain all languages and need no pack.

---

## 📥 Getting a Language Pack

- **Standard Flavor**: Open **Settings → Languages & Layouts → App translation** in LeanType to download the language pack for your locale.
- **Offline Flavor**: Download the matching pack APK from the [Releases](https://github.com/LeanBitLab/LeanType-Language-Packs/releases) section of this repository and import it via **Settings → Languages & Layouts → App translation**.

---

## 🔄 Compatibility Across Updates

Each language pack is built for a specific LeanType build and is coupled to that build's exact resource structure. Release tags in this repository follow the format `<versionName>-<crc32 of resources.arsc>`.

> [!IMPORTANT]
> When you update the LeanType app, previously downloaded packs will not match the new build. You must update or re-download the language pack so its release tag matches your updated app build.

---

## 🛠️ Maintainer Guide: Building Language Packs

### Automated Build Workflow

Language pack releases are generated via GitHub Actions:

1. When a LeanType release is published, its workflow starts "Build language packs" with the release tag.
2. To build for a specific release, run it from the **Actions** tab with the LeanType release tag (e.g. `v4.3.7`).
3. The workflow fetches the English-only APKs (standard and offline), builds packs for every locale with `tools/build_language_pack.py`, and publishes releases tagged by `<versionName>-<crc32>`.

### Local Build Command

To build a pack locally, use the script from the [LeanType repository](https://github.com/LeanBitLab/LeanType):

```bash
python3 tools/build_language_pack.py --apk <app.apk> --locale de --out-dir packs
```

---

## 📜 License

This project is licensed under the [GNU General Public License v3.0](LICENSE) (GPL-3.0), matching LeanType.

## 💖 Support the Development

If you find this project helpful, consider supporting the continuous development of the LeanType ecosystem:

<div align="left">
  <a href="https://github.com/sponsors/LeanBitLab" target="_blank">
    <img src="https://img.shields.io/badge/Sponsor-GitHub%20Sponsors-EA4AAA?style=for-the-badge&logo=githubsponsors&logoColor=white" alt="GitHub Sponsors" />
  </a>
  <a href="https://opencollective.com/leanbitlab-org" target="_blank">
    <img src="https://img.shields.io/badge/Donate-Open%20Collective-7B93FE?style=for-the-badge&logo=opencollective&logoColor=white" alt="Open Collective" />
  </a>
</div>
