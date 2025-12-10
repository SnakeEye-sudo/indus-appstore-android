# Indus Appstore Android App Deployment

Automated Android app deployment to Indus Appstore using GitHub Actions with PhonePe/Indus-Flows workflow.

## Overview

This repository demonstrates a complete CI/CD pipeline for deploying Android applications to the Indus Appstore. It uses the official **PhonePe/Indus-Flows** GitHub Action to automate the deployment process for APK, AAB (Android App Bundle), and APKS (Android Package Split) formats.

## Features

✅ Automated deployment to Indus Appstore  
✅ Supports APK, AAB, and APKS formats  
✅ Triggered on release publication  
✅ Manual workflow dispatch support  
✅ GitHub Actions integration  
✅ Encrypted secrets for API credentials  

## Quick Start

### 1. Setup Repository

Clone this repository or use it as a template for your Android project.

```bash
git clone https://github.com/SnakeEye-sudo/indus-appstore-android.git
cd indus-appstore-android
```

### 2. Configure GitHub Secrets

Add the following secrets in repository settings (Settings → Secrets and variables → Actions):

- `INDUS_API_KEY` - Your PhonePe Indus Appstore API key

```bash
# You can also add additional secrets if needed:
# INDUS_APP_ID - Your app's Indus Appstore ID
```

### 3. Update Workflow Configuration

Edit `.github/workflows/release.yml` and configure:

```yaml
- name: Deploy to Indus Appstore
  uses: PhonePe/Indus-Flows@v1
  with:
    app_bundle_path: 'app/build/outputs/bundle/release/app-release.aab'
    api_key: ${{ secrets.INDUS_API_KEY }}
    # Add other required configuration
```

### 4. Build Your Android App

Add your Android build configuration to the workflow.

## Workflow Details

**Location:** `.github/workflows/release.yml`

**Triggers:**
- `release`: When a release is published
- `workflow_dispatch`: Manual trigger from Actions tab

**Jobs:**
1. Checkout repository code
2. Build Android App (add your build commands)
3. Deploy to Indus Appstore using PhonePe/Indus-Flows

## Requirements

- Android project with Gradle build system
- PhonePe Indus Appstore developer account
- Valid API credentials
- GitHub repository with Actions enabled

## Documentation

- [PhonePe/Indus-Flows Action Documentation](https://github.com/PhonePe/Indus-Flows)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Indus Appstore Developer Guide](https://www.myindusapp.com/)

## Contributing

Feel free to submit issues and enhancement requests!

## License

MIT License - feel free to use this for your projects

---

**Made with ❤️ by SnakeEye-sudo**
