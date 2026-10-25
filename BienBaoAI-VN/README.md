# Biển Báo AI – bản dữ liệu Việt Nam

App nhận diện biển báo giao thông chạy ngoại tuyến. Mô hình CNN giống bản GTSRB (kiến trúc `traffic_sign.py`), huấn luyện trên bộ dữ liệu biển báo Việt Nam `maitam/vietnamese-traffic-signs` (Kaggle).
Cài song song được với app bản GTSRB (tên app "Biển Báo AI VN", mã ứng dụng `vn.khkt.vn.bien_bao_ai`).

## Cấu trúc
- `notebook/CNN_bien_bao_VietNam_maitam.ipynb` – huấn luyện trên Google Colab (T4 GPU → Run all)
- `assets/` – `model.tflite`, `signs.json`, `signs/<id>.png` (ảnh minh họa từng loại biển)
- `lib/` – mã nguồn Flutter
- `.github/workflows/build-apk.yml` – GitHub tự build APK mỗi lần đẩy code lên nhánh `main`

## Cập nhật mô hình
1. Chạy notebook trên Colab, tải về `assets_app.zip`.
2. Xóa hết ảnh trong `assets/signs/`, giải nén `assets_app.zip` đè vào `assets/`.
3. Đẩy lên GitHub → tab **Actions** → chờ build xong → tải `BienBaoAI-VN-APK`.

> Lúc mới tạo, `assets/` đang chứa mô hình GTSRB 43 lớp để app build được ngay; thay bằng mô hình Việt Nam ở bước trên.
