# 🚀 Setup Guide - VietmediaF Kodi Addon Repository

Hướng dẫn thiết lập và triển khai repository để tự động build và deploy addon VietmediaF lên GitHub Pages.

## 📋 Yêu cầu trước khi bắt đầu

- [x] GitHub account
- [x] Git đã được cài đặt
- [x] Repository đã được tạo trên GitHub

## 🔧 Thiết lập Repository

### 1. Clone và Push Code

```bash
# Clone repository của bạn
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
cd YOUR-REPOSITORY

# Copy addon code vào repository
cp -r /path/to/kodivmf/* .

# Add và commit files
git add .
git commit -m "Initial commit: Add VietmediaF Kodi addon"
git push origin main
```

### 2. Cấu hình GitHub Pages

1. **Truy cập repository settings**:
   - Vào `https://github.com/YOUR-USERNAME/YOUR-REPOSITORY/settings`

2. **Thiết lập Pages**:
   - Scroll xuống section **"Pages"**
   - **Source**: Chọn **"GitHub Actions"**
   - Click **"Save"**

### 3. Cập nhật URLs trong README.md

Thay thế các placeholder trong `README.md`:

```bash
# Thay thế USERNAME và REPOSITORY bằng thông tin thực của bạn
sed -i 's/USERNAME/your-github-username/g' README.md
sed -i 's/REPOSITORY/your-repository-name/g' README.md
```

Hoặc thủ công thay thế:
- `USERNAME` → username GitHub của bạn
- `REPOSITORY` → tên repository của bạn

## 🤖 GitHub Actions Workflow

### Workflow hoạt động như thế nào?

Workflow sẽ tự động chạy khi:
- ✅ Push code to `main` hoặc `master` branch
- ✅ Tạo Pull Request
- ✅ Tạo GitHub Release

### Các bước workflow thực hiện:

1. **📖 Đọc version**: Tự động lấy version từ `plugin.video.vietmediaF/addon.xml`
2. **📦 Tạo ZIP**: Đóng gói addon thành file ZIP
3. **🔐 Tạo checksum**: Sinh SHA256 hash để verify tính toàn vẹn
4. **🏗️ Build repository**: Tạo cấu trúc Kodi repository
5. **🌐 Deploy**: Upload lên GitHub Pages

### Kiểm tra workflow

Sau khi push code, kiểm tra:
- **Actions tab**: `https://github.com/YOUR-USERNAME/YOUR-REPOSITORY/actions`
- **Pages deployment**: Sẽ mất 2-5 phút để deploy

## 📂 Cấu trúc Files sau khi Deploy

```
https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/
├── index.html                                    # Trang chủ với download links
├── addons.xml                                   # Kodi repository index
├── addons.xml.md5                              # MD5 checksum
├── plugin.video.vietmediaF.zip                 # Latest version
├── plugin.video.vietmediaF-VERSION.zip         # Specific version
├── plugin.video.vietmediaF-VERSION.zip.sha256  # SHA256 checksum
└── plugin.video.vietmediaF/
    ├── addon.xml                               # Addon metadata
    ├── icon.png                                # Addon icon
    └── fanart.png                              # Fanart image
```

## 🔄 Quy trình phát triển

### Cập nhật version

1. **Sửa version trong addon.xml**:
   ```xml
   <addon id="plugin.video.vietmediaF" name="VietmediaF" version="11.37.5">
   ```

2. **Commit và push**:
   ```bash
   git add plugin.video.vietmediaF/addon.xml
   git commit -m "Bump version to 11.37.5"
   git push origin main
   ```

3. **Workflow sẽ tự động**:
   - Tạo file ZIP mới với version mới
   - Update repository files
   - Deploy lên GitHub Pages

### Tạo GitHub Release (Optional)

```bash
# Tạo tag cho version mới
git tag -a v11.37.5 -m "Release version 11.37.5"
git push origin v11.37.5

# Hoặc tạo release trực tiếp trên GitHub web interface
```

## 🧪 Testing

### Test local

```bash
# Check addon.xml syntax
xmllint --noout plugin.video.vietmediaF/addon.xml

# Create test zip manually
cd plugin.video.vietmediaF
zip -r ../plugin.video.vietmediaF-test.zip . -x "*.git*" "*.DS_Store*"
cd ..
```

### Test deployment

1. **Check Actions**: Workflow chạy thành công?
2. **Check Pages**: `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/`
3. **Download test**: Tải file ZIP và test trong Kodi

## 🛠️ Troubleshooting

### GitHub Actions fails

**Lỗi thường gặp:**

1. **Permission denied**:
   ```yaml
   # Đảm bảo workflow có permission
   permissions:
     contents: read
     pages: write
     id-token: write
   ```

2. **addon.xml not found**:
   - Kiểm tra path: `plugin.video.vietmediaF/addon.xml`
   - Đảm bảo file tồn tại

3. **Version parsing error**:
   - Kiểm tra format version trong addon.xml
   - Format phải là: `version="x.y.z"`

### GitHub Pages không hiển thị

1. **Check Pages settings**: Source = "GitHub Actions"
2. **Check Actions logs**: Workflow deploy thành công?
3. **Wait**: Đôi khi cần đợi 5-10 phút
4. **Check URL**: `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/`

### Download link không hoạt động

1. **Check file exists**: Files được tạo trong workflow?
2. **Check permissions**: Repository public?
3. **Check URL format**: Đúng case-sensitive?

## 🔒 Security Best Practices

### Repository Security

1. **Public vs Private**:
   - Repository có thể public (recommended)
   - GitHub Pages hoạt động với cả public và private repos

2. **Secrets management**:
   - Không commit passwords/tokens
   - Sử dụng GitHub Secrets nếu cần

3. **Branch protection**:
   ```bash
   # Setup branch protection rules cho main branch
   # Settings > Branches > Add rule
   ```

## 📊 Monitoring

### Check deployment status

```bash
# GitHub CLI (nếu đã cài)
gh run list
gh run view [RUN_ID]

# Check Pages status
curl -I https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/
```

### Analytics

GitHub cung cấp insights về:
- Repository traffic
- Download statistics (nếu public)
- Actions usage

## 🎯 Next Steps

Sau khi setup thành công:

1. **✅ Test addon**: Install và test trong Kodi
2. **📢 Share**: Chia sẻ repository URL với community
3. **📝 Documentation**: Update README với thông tin cụ thể
4. **🔄 Maintenance**: Regular updates và bug fixes

## 📞 Support

Nếu gặp vấn đề:

1. **Check logs**: GitHub Actions logs
2. **GitHub Issues**: Tạo issue với error details
3. **GitHub Discussions**: Thảo luận với community

---

**🎉 Chúc mừng! Repository của bạn đã sẵn sàng để distribute VietmediaF addon!**