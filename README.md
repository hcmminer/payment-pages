# LeetCode Interview Assistant - Payment Pages

Trang web hiển thị trạng thái thanh toán cho LeetCode Interview Assistant Extension.

## Cách setup GitHub Pages

### 1. Tạo repository mới trên GitHub
- Tạo repository mới với tên: `payment-pages` hoặc tên bạn muốn
- Repository phải là public để sử dụng GitHub Pages miễn phí

### 2. Upload files
Upload các file sau vào repository:
- `success.html` - Trang thành công
- `cancel.html` - Trang hủy thanh toán
- `README.md` - File này

### 3. Kích hoạt GitHub Pages
1. Vào repository → Settings
2. Scroll xuống phần "Pages"
3. Source: chọn "Deploy from a branch"
4. Branch: chọn "main" hoặc "master"
5. Folder: chọn "/ (root)"
6. Click "Save"

### 4. Cập nhật Extension ID
**Quan trọng:** Bạn cần thay thế `YOUR_EXTENSION_ID_HERE` bằng Extension ID thực tế:

1. Mở Chrome → `chrome://extensions/`
2. Bật Developer mode
3. Load extension từ thư mục `frontend`
4. Copy Extension ID (dãy ký tự dài màu xanh)
5. Thay thế `YOUR_EXTENSION_ID_HERE` trong các file:
   - `success.html` (dòng có link "Quay lại Extension")
   - `cancel.html` (2 dòng có link "Thử lại" và "Quay lại Extension")

### 5. Cập nhật URL trong backend
Sau khi GitHub Pages được kích hoạt, URL sẽ có dạng:
```
https://yourusername.github.io/payment-pages/
```

Cập nhật trong file `backend/src/routes/premium.ts`:
```typescript
success_url: `https://yourusername.github.io/payment-pages/success.html?session_id={CHECKOUT_SESSION_ID}`,
cancel_url: `https://yourusername.github.io/payment-pages/cancel.html`,
```

### 6. Test
- Truy cập: `https://yourusername.github.io/payment-pages/success.html`
- Truy cập: `https://yourusername.github.io/payment-pages/cancel.html`

## Tính năng

### Trang Success (success.html)
- ✅ Hiển thị thông báo thanh toán thành công
- ✅ Liệt kê các tính năng Premium
- ✅ Nút quay lại extension
- ✅ Design responsive và đẹp mắt

### Trang Cancel (cancel.html)
- ❌ Hiển thị thông báo hủy thanh toán
- 💡 Gợi ý các bước tiếp theo
- 🔄 Nút thử lại thanh toán
- 🏠 Nút quay lại extension

## Customization

Bạn có thể tùy chỉnh:
- Màu sắc trong CSS
- Nội dung text
- Logo và branding
- Thêm analytics tracking
- Thêm social media links

## Lưu ý

- **Đảm bảo Extension ID chính xác** - đây là bước quan trọng nhất
- Test kỹ trước khi deploy production
- Có thể thêm loading animation và transition effects 