# UI2Py Factory Automation - Công cụ chuyển đổi UI sang Python

UI2Py là một ứng dụng đồ họa giúp chuyển đổi file UI của Qt Designer sang mã Python một cách nhanh chóng và tiện lợi. Công cụ này cung cấp giao diện người dùng dễ sử dụng, hỗ trợ kéo thả và có nhiều tính năng hữu ích khác.

![UI2Py Screenshot](screenshot.png)

## Tính năng

- Giao diện người dùng hiện đại và thân thiện
- Hỗ trợ kéo thả file UI trực tiếp vào ứng dụng
- Chuyển đổi nhiều file cùng lúc
- Hiển thị trạng thái chuyển đổi rõ ràng
- Mở thư mục chứa file đã chuyển đổi ngay trong ứng dụng
- Giao diện tối (Dark Mode) dễ chịu cho mắt

## Yêu cầu hệ thống

- Python 3.6 hoặc cao hơn
- PyQt5
- pyuic5 (công cụ chuyển đổi UI của Qt)

## Cài đặt

1. Cài đặt Python từ [python.org](https://www.python.org/downloads/)
2. Cài đặt PyQt5 bằng pip:

```bash
pip install PyQt5
```
3. Chạy ứng dụng:

```bash
python main.py
```

## Cách sử dụng

### Phương pháp 1: Kéo thả

1. Mở ứng dụng UI2Py
2. Kéo một hoặc nhiều file .ui từ File Explorer/Finder vào vùng kéo thả trong ứng dụng
3. Nhấp vào nút "Chuyển đổi" để tạo file Python
4. File Python đã chuyển đổi sẽ được lưu cùng thư mục với file UI gốc
5. Nhấp vào "Mở File Convert" để xem kết quả

### Phương pháp 2: Sử dụng nút "Mở File"

1. Mở ứng dụng UI2Py
2. Nhấp vào nút "Mở File"
3. Chọn một hoặc nhiều file .ui trong hộp thoại mở file
4. Nhấp vào nút "Chuyển đổi" để tạo file Python
5. File Python đã chuyển đổi sẽ được lưu cùng thư mục với file UI gốc
6. Nhấp vào "Mở File Convert" để xem kết quả

## Sử dụng file đã chuyển đổi

File Python đã chuyển đổi có thể được import vào dự án PyQt5 của bạn như sau:

```python
from PyQt5 import QtWidgets
import design  # Giả sử file UI đã được chuyển đổi thành design.py

class MyApp(QtWidgets.QMainWindow, design.Ui_MainWindow):
    def __init__(self):
        super().__init__()
        self.setupUi(self)
        # Thêm mã của bạn ở đây

if __name__ == '__main__':
    app = QtWidgets.QApplication([])
    window = MyApp()
    window.show()
    app.exec_()
```

## Khắc phục sự cố

### Lỗi "pyuic5 không được nhận dạng"

Nếu bạn gặp lỗi "pyuic5 không được nhận dạng", hãy thử một trong các cách sau:

1. Đảm bảo PyQt5 đã được cài đặt đúng cách:
   ```bash
   pip install --upgrade PyQt5 PyQt5-tools
   ```

2. Sử dụng python -m trực tiếp:
   ```bash
   python -m PyQt5.uic.pyuic file.ui -o file.py
   ```

3. Tạo file batch pyuic5.bat trong thư mục Python\Scripts với nội dung:
   ```
   @echo off
   python -m PyQt5.uic.pyuic %1 %2 %3 %4 %5 %6 %7 %8 %9
   ```

4. Thêm đường dẫn đến thư mục Scripts vào biến môi trường PATH

## Liên hệ & Hỗ trợ

Nếu bạn có câu hỏi hoặc gặp vấn đề, vui lòng tạo issue trên GitHub hoặc liên hệ trực tiếp với tác giả.

## Ủng hộ phát triển

Nếu bạn thấy ứng dụng này hữu ích, bạn có thể ủng hộ tác giả bằng cách nhấp vào mục "Ủng hộ" trong menu của ứng dụng.

## Tác giả

Ứng dụng UI2Py được phát triển bởi **Factory Automation**. Nếu bạn sử dụng ứng dụng này trong dự án của mình, hãy ghi nhận công sức phát triển bằng cách giữ nguyên thông tin tác giả và xem xét ủng hộ cho công việc phát triển.

## Giấy phép

Phần mềm được phát hành theo giấy phép MIT.

---

© 2023 Factory Automation - Tất cả các quyền được bảo lưu 