<h1 align="center">LineageOS for Pixel 4</h1>

<div align="center">

<p><i>OTA update support for the Google Pixel 4 (flame), providing the latest available LineageOS builds.</i></p>

[![LineageOS](https://img.shields.io/badge/LineageOS-167C80?style=for-the-badge\&logo=lineageos\&logoColor=white)](https://lineageos.org/)
[![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge\&logo=android\&logoColor=white)](https://www.android.com/)
[![AOSP](https://img.shields.io/badge/AOSP-3DDC84?style=for-the-badge\&logo=android\&logoColor=white)](https://source.android.com/)
[![OTA](https://img.shields.io/badge/OTA-Update-167C80?style=for-the-badge\&logo=android\&logoColor=white)](#)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge\&logo=github\&logoColor=white)](https://github.com/)
[![Active](https://img.shields.io/badge/Status-Active-2EA44F?style=for-the-badge)](#)

</div>

## About

This repository contains the OTA metadata required to provide update information for the Google Pixel 4 (`flame`).

The repository is intentionally minimal and contains the update configuration used by the LineageOS updater.

## Device

| Property      | Value          |
| ------------- | -------------- |
| Device        | Google Pixel 4 |
| Codename      | `flame`        |
| ROM           | LineageOS      |
| Update method | OTA            |
| Architecture  | ARM64          |

## Repository Structure

```text
.
└── flame.json
```

## OTA

The `flame.json` file contains the information required by the updater to detect and provide available OTA builds for the device.

> **Note:** This repository only provides OTA metadata. The actual LineageOS builds are hosted separately.

## Disclaimer

This is an unofficial project and is not affiliated with or endorsed by the LineageOS project or Google.
