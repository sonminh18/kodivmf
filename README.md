# 🎬 VietmediaF Kodi Addon Repository

[![Build and Deploy](https://github.com/USERNAME/REPOSITORY/actions/workflows/deploy.yml/badge.svg)](https://github.com/USERNAME/REPOSITORY/actions/workflows/deploy.yml)
[![GitHub release](https://img.shields.io/github/release/USERNAME/REPOSITORY.svg)](https://github.com/USERNAME/REPOSITORY/releases)
[![Kodi version](https://img.shields.io/badge/kodi-21%2B-blue.svg)](https://kodi.tv/)

> **VietmediaF** - Addon tổng hợp link fshare được chia sẻ trên Internet cho Kodi

## 📖 Giới thiệu

VietmediaF là một addon dành cho Kodi được thiết kế đặc biệt để tổng hợp và truy cập các nội dung media tiếng Việt từ các dịch vụ chia sẻ file như Fshare và 4share. Addon cung cấp giao diện thân thiện với người dùng Việt Nam và tích hợp nhiều nguồn nội dung phong phú.

### ✨ Tính năng chính

- 🔗 **Tích hợp Fshare & 4Share**: Hỗ trợ đăng nhập và truy cập tài khoản VIP
- 🎥 **Đa nguồn nội dung**: ThuvienCine, ThuvienHD, HDVietNam và nhiều nguồn khác
- 📱 **Đăng nhập QR Code**: Đăng nhập nhanh chóng qua mã QR
- 📥 **Tải xuống tích hợp**: Tải file trực tiếp từ addon
- 📺 **Hỗ trợ IPTV**: Xem các kênh truyền hình trực tuyến
- 🔍 **Tìm kiếm thông minh**: Tìm kiếm nội dung từ nhiều nguồn
- 📖 **Phụ đề tự động**: Tự động tải phụ đề nếu có trong thư mục
- 🎨 **Giao diện tùy chỉnh**: Hỗ trợ skin và theme tùy chỉnh

## 🚀 Cài đặt nhanh

### Cách 1: Tải xuống trực tiếp
1. Truy cập [trang tải xuống](https://USERNAME.github.io/REPOSITORY/)
2. Tải file `plugin.video.vietmediaF.zip`
3. Cài đặt trong Kodi: **Settings > Add-ons > Install from zip file**

### Cách 2: Thêm Repository
1. Mở Kodi và vào **File Manager**
2. Chọn **Add source** và nhập URL:
   ```
   https://USERNAME.github.io/REPOSITORY/
   ```
3. Vào **Settings > Add-ons > Install from repository**
4. Tìm repository **VietmediaF** và cài đặt addon

## 🛠️ Phát triển

### Cấu trúc dự án
```
kodivmf/
├── .github/workflows/          # GitHub Actions workflows
│   └── deploy.yml             # Build và deploy tự động
├── plugin.video.vietmediaF/   # Mã nguồn addon chính
│   ├── addon.xml             # Cấu hình addon
│   ├── default.py            # Entry point chính
│   ├── resources/            # Modules và resources
│   └── ...                   # Các file khác
├── SETUP.md                  # Hướng dẫn setup chi tiết
├── LICENSE                   # MIT license
├── .gitignore               # Git exclusions
└── README.md                # File này
```

### GitHub Actions Workflow

Repository này sử dụng GitHub Actions để tự động:

1. **🔍 Phát hiện phiên bản**: Tự động đọc version từ `addon.xml`
2. **📦 Đóng gói**: Tạo file ZIP từ source code
3. **🔐 Tạo checksum**: Sinh SHA256 hash cho bảo mật
4. **🌐 Deploy GitHub Pages**: Tự động cập nhật trang tải xuống
5. **📋 Tạo Kodi Repository**: Tạo cấu trúc repository chuẩn Kodi

#### Workflow triggers:
- ✅ Push to `main/master` branch
- ✅ Pull request to `main/master`
- ✅ GitHub Releases

### Cài đặt môi trường phát triển

1. **Clone repository**:
   ```bash
   git clone https://github.com/USERNAME/REPOSITORY.git
   cd REPOSITORY
   ```

2. **Thiết lập GitHub Pages**:
   - Vào **Settings > Pages**
   - Source: **GitHub Actions**
   - Workflow sẽ tự động chạy khi push code

3. **Cập nhật version**:
   ```xml
   <!-- Trong file plugin.video.vietmediaF/addon.xml -->
   <addon id="plugin.video.vietmediaF" name="VietmediaF" version="11.37.5">
   ```

## 📋 Yêu cầu hệ thống

- **Kodi**: Phiên bản 21 (Omega) trở lên
- **Python**: 3.0+
- **Dependencies**: 
  - `script.module.six`
  - `script.module.requests`
  - `script.module.beautifulsoup4`

## 🔧 Cấu hình

### Fshare/4Share Account
1. Mở addon settings
2. Nhập username/password Fshare
3. Hoặc sử dụng QR Code để đăng nhập nhanh

### Custom Sources
- Addon hỗ trợ thêm nguồn nội dung tùy chỉnh
- Cấu hình trong **Advanced Settings**

## 📚 Tài liệu API

### Repository URL Structure
```
https://USERNAME.github.io/REPOSITORY/
├── addons.xml              # Kodi repository index
├── addons.xml.md5         # MD5 hash của addons.xml
├── plugin.video.vietmediaF.zip           # Latest version
├── plugin.video.vietmediaF-VERSION.zip   # Specific version
└── plugin.video.vietmediaF/
    ├── addon.xml          # Addon metadata
    ├── icon.png          # Addon icon
    └── fanart.png        # Fanart image
```

## 📄 License

Dự án này được phát hành dưới MIT License. Xem file [LICENSE](LICENSE) để biết thêm chi tiết.

## ⚠️ Disclaimer

Addon này chỉ tổng hợp các link được chia sẻ công khai trên Internet. Tác giả không chịu trách nhiệm về:
- Tính hợp pháp của nội dung
- Bản quyền của nội dung được chia sẻ
- Chất lượng hoặc tính chính xác của nội dung

Người dùng có trách nhiệm tuân thủ luật pháp và bản quyền tại quốc gia của mình.

## 🤝 Đóng góp

Chúng tôi hoan nghênh mọi đóng góp! Vui lòng:

1. Fork repository
2. Tạo feature branch: `git checkout -b feature/AmazingFeature`
3. Commit changes: `git commit -m 'Add AmazingFeature'`
4. Push to branch: `git push origin feature/AmazingFeature`
5. Tạo Pull Request

## 📞 Hỗ trợ

- 🐛 **Bug Reports**: [GitHub Issues](https://github.com/USERNAME/REPOSITORY/issues)
- 💡 **Feature Requests**: [GitHub Discussions](https://github.com/USERNAME/REPOSITORY/discussions)
- 📧 **Email**: your-email@domain.com

## 📊 Thống kê

![GitHub stars](https://img.shields.io/github/stars/USERNAME/REPOSITORY?style=social)
![GitHub forks](https://img.shields.io/github/forks/USERNAME/REPOSITORY?style=social)
![GitHub issues](https://img.shields.io/github/issues/USERNAME/REPOSITORY)
![GitHub pull requests](https://img.shields.io/github/issues-pr/USERNAME/REPOSITORY)

---

<div align="center">
  <p>🎬 <strong>Hãy thưởng thức những bộ phim yêu thích của bạn!</strong> 🍿</p>
  <p>Được xây dựng với ❤️ cho cộng đồng Kodi Việt Nam</p>
</div>