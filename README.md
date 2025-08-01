# 🎬 VietmediaF Kodi Addon Repository

[![Build and Deploy](https://github.com/sonminh18/kodivmf/actions/workflows/deploy.yml/badge.svg)](https://github.com/sonminh18/kodivmf/actions/workflows/deploy.yml)
[![GitHub release](https://img.shields.io/github/release/sonminh18/kodivmf.svg)](https://github.com/sonminh18/kodivmf/releases)
[![Kodi version](https://img.shields.io/badge/kodi-21%2B-blue.svg)](https://kodi.tv/)

> **VietmediaF** - A Kodi addon that aggregates Fshare links shared on the Internet

## 📖 About

VietmediaF is a Kodi addon specially designed to aggregate and access Vietnamese media content from file sharing services like Fshare and 4share. The addon provides a user-friendly interface for Vietnamese users and integrates multiple rich content sources.

### ✨ Key Features

- 🔗 **Fshare & 4Share Integration**: Login support and VIP account access
- 🎥 **Multiple Content Sources**: ThuvienCine, ThuvienHD, HDVietNam and many others
- 📱 **QR Code Login**: Quick login via QR code
- 📥 **Integrated Downloads**: Download files directly from the addon
- 📺 **IPTV Support**: Watch live TV channels
- 🔍 **Smart Search**: Search content from multiple sources
- 📖 **Automatic Subtitles**: Auto-load subtitles if available in folder
- 🎨 **Custom Interface**: Support for custom skins and themes

## 🚀 Quick Installation

### Method 1: Direct Download
1. Visit the [download page](https://sonminh18.github.io/kodivmf/)
2. Download `plugin.video.vietmediaF.zip`
3. Install in Kodi: **Settings > Add-ons > Install from zip file**

### Method 2: Add Repository
1. Open Kodi and go to **File Manager**
2. Select **Add source** and enter URL:
   ```
   https://sonminh18.github.io/kodivmf/
   ```
3. Go to **Settings > Add-ons > Install from repository**
4. Find **VietmediaF** repository and install the addon

## 🛠️ Development

### Project Structure
```
kodivmf/
├── .github/workflows/          # GitHub Actions workflows
│   └── deploy.yml             # Automated build and deploy
├── plugin.video.vietmediaF/   # Main addon source code
│   ├── addon.xml             # Addon configuration
│   ├── default.py            # Main entry point
│   ├── resources/            # Modules and resources
│   └── ...                   # Other files
├── SETUP.md                  # Detailed setup guide
├── LICENSE                   # MIT license
├── .gitignore               # Git exclusions
└── README.md                # This file
```

### GitHub Actions Workflow

This repository uses GitHub Actions to automatically:

1. **🔍 Version Detection**: Automatically read version from `addon.xml`
2. **📦 Packaging**: Create ZIP file from source code
3. **🔐 Create Checksum**: Generate SHA256 hash for security
4. **🌐 Deploy GitHub Pages**: Automatically update download page
5. **📋 Create Kodi Repository**: Create standard Kodi repository structure

#### Workflow triggers:
- ✅ Push to `main/master` branch
- ✅ Pull request to `main/master`
- ✅ GitHub Releases

### Development Environment Setup

1. **Clone repository**:
   ```bash
   git clone https://github.com/sonminh18/kodivmf.git
   cd kodivmf
   ```

2. **Setup GitHub Pages**:
   - Go to **Settings > Pages**
   - Source: **GitHub Actions**
   - Workflow will run automatically when pushing code

3. **Update version**:
   ```xml
   <!-- In file plugin.video.vietmediaF/addon.xml -->
   <addon id="plugin.video.vietmediaF" name="VietmediaF" version="11.37.5">
   ```

## 📋 System Requirements

- **Kodi**: Version 21 (Omega) or higher
- **Python**: 3.0+
- **Dependencies**: 
  - `script.module.six`
  - `script.module.requests`
  - `script.module.beautifulsoup4`

## 🔧 Configuration

### Fshare/4Share Account
1. Open addon settings
2. Enter Fshare username/password
3. Or use QR Code for quick login

### Custom Sources
- Addon supports adding custom content sources
- Configure in **Advanced Settings**

## 📚 API Documentation

### Repository URL Structure
```
https://sonminh18.github.io/kodivmf/
├── addons.xml              # Kodi repository index
├── addons.xml.md5         # MD5 hash of addons.xml
├── plugin.video.vietmediaF.zip           # Latest version
├── plugin.video.vietmediaF-VERSION.zip   # Specific version
└── plugin.video.vietmediaF/
    ├── addon.xml          # Addon metadata
    ├── icon.png          # Addon icon
    └── fanart.png        # Fanart image
```

## 📄 License

This project is released under the MIT License. See the [LICENSE](LICENSE) file for more details.

## ⚠️ Disclaimer

This addon only aggregates links shared publicly on the Internet. The author is not responsible for:
- Legality of content
- Copyright of shared content
- Quality or accuracy of content

Users are responsible for complying with copyright laws and regulations in their country.

## 🤝 Contributing

We welcome all contributions! Please:

1. Fork the repository
2. Create feature branch: `git checkout -b feature/AmazingFeature`
3. Commit changes: `git commit -m 'Add AmazingFeature'`
4. Push to branch: `git push origin feature/AmazingFeature`
5. Create Pull Request

## 📞 Support

- 🐛 **Bug Reports**: [GitHub Issues](https://github.com/sonminh18/kodivmf/issues)
- 💡 **Feature Requests**: [GitHub Discussions](https://github.com/sonminh18/kodivmf/discussions)
- 📧 **Email**: your-email@domain.com

## 📊 Statistics

![GitHub stars](https://img.shields.io/github/stars/sonminh18/kodivmf?style=social)
![GitHub forks](https://img.shields.io/github/forks/sonminh18/kodivmf?style=social)
![GitHub issues](https://img.shields.io/github/issues/sonminh18/kodivmf)
![GitHub pull requests](https://img.shields.io/github/issues-pr/sonminh18/kodivmf)

---

<div align="center">
  <p>🎬 <strong>Enjoy your favorite movies!</strong> 🍿</p>
  <p>Built with ❤️ for the Vietnamese Kodi community</p>
</div>