# Asteroids (Nothing Phone 3a / 3a Pro) Local Manifest for AOSPA (Paranoid Android)

This repository contains the local manifests for building AOSPA (branch `calcite`) for the Nothing Phone (3a) and Nothing Phone (3a) Pro (codenamed `asteroids`).

## Quick Setup

### 1. Initialize AOSPA tree

```bash
repo init -u https://github.com/AOSPA/manifest -b calcite
```

### 2. Add Asteroids local manifests

Clone or copy these manifest files into `.repo/local_manifests/`:

```bash
mkdir -p .repo/local_manifests
curl -sL https://raw.githubusercontent.com/Asteroids-AOSPA/android_manifest/calcite/asteroids.xml > .repo/local_manifests/asteroids.xml
curl -sL https://raw.githubusercontent.com/Asteroids-AOSPA/android_manifest/calcite/pineapple-kernel.xml > .repo/local_manifests/pineapple-kernel.xml
```

### 3. Sync the tree

```bash
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

### 4. Build

```bash
. build/envsetup.sh
lunch aospa_asteroids-userdebug
./rom-build.sh asteroids
```
Or directly using m:
```bash
m bacon -j$(nproc --all)
```
