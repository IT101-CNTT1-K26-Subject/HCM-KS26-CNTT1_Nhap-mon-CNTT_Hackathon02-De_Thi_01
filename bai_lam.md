# BÀI LÀM – HACKATHON 02

- **Mã đề:De Thi 01 IT108 Hackathon02** 01
- **Họ tên:Nguyễn Duy Minh Hà**
- **Lớp:HCM-CNTT01**
- **Link repository:https://github.com/IT101-CNTT1-K26-Subject/HCM-KS26-CNTT1_Nhap-mon-CNTT_Hackathon02.git**
- **Hệ điều hành (Windows/macOS): Windows**

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
ls -Force
mv .\ghi_chu_ban_giao.txt .\docs\
mkdir backup
cp .\data\ban_ve_thang_1.xlsx .\backup\
rm *.tmp
cd .\logs\
ls
cd ..

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
  Directory: C:\Users\Admin\OneDrive\Dokumente\IT101\starter-kit\ho-boi-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
dar--l        11/11/2026   7:57 AM                backup
dar--l        11/11/2026   7:54 AM                data
dar--l        11/11/2026   7:56 AM                docs
dar--l        11/11/2026   7:52 AM                evidence
dar--l        11/11/2026   7:53 AM                logs
dar--l        11/11/2026   7:49 AM                web
-a---l         11/3/2026   7:06 AM             74 .env
-a---l         11/3/2026   7:06 AM           2407 bai_lam.md


    Directory: C:\Users\Admin\OneDrive\Dokumente\IT101\starter-kit\ho-boi-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---l         11/3/2026   7:06 AM           6106 ban_ve_thang_1.xlsx


    Directory: C:\Users\Admin\OneDrive\Dokumente\IT101\starter-kit\ho-boi-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---l         11/3/2026   7:06 AM           6106 ban_ve_thang_1.xlsx


    Directory: C:\Users\Admin\OneDrive\Dokumente\IT101\starter-kit\ho-boi-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---l         11/3/2026   7:06 AM            158 ghi_chu_ban_giao.txt


    Directory: C:\Users\Admin\OneDrive\Dokumente\IT101\starter-kit\ho-boi-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---l         11/3/2026   7:06 AM            972 visit.log


    Directory: C:\Users\Admin\OneDrive\Dokumente\IT101\starter-kit\ho-boi-website\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
dar--l        11/11/2026   7:49 AM                images
-a---l         11/3/2026   7:06 AM            574 app.js
-a---l         11/3/2026   7:06 AM            507 index.html
-a---l         11/3/2026   7:06 AM            460 style.css


    Directory: C:\Users\Admin\OneDrive\Dokumente\IT101\starter-kit\ho-boi-website\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---l         11/3/2026   7:06 AM           3061 logo-aquazone.png

```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
Select-String "status=500" .\logs\visit.log > .\logs\loi_500.txt

```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
logs\visit.log:8:2026-01-28 08:24:34 POST /api/thanh-toan status=500
logs\visit.log:9:2026-01-28 08:28:45 POST /api/thanh-toan status=500

```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
(Get-Content .\logs\visit.log | Select-String "status=404").Count

```

```text
4

```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\tong_hop.ps1
```

### Nội dung file logs/tong_hop.txt

```text
=== BAO CAO SU CO WEBSITE ===

2026-01-28 08:07:39 GET /tin-tuc status=404
2026-01-28 08:13:01 GET /ve-cu status=404
2026-01-28 08:34:07 GET /images/be-boi-2.jpg status=404
2026-01-28 08:57:24 GET /khuyen-mai-he status=404




Count    : 6
Average  :
Sum      :
Maximum  :
Minimum  :
Property :




```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [X] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [X] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [X] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 | Network | logo.png | Sửa logo.png thành logo-aquazone.png |
| 2 | Console | Uncaught ReferenceError: hienThiBangGia is not defined | Sửa "hienthiBangGia" ở dòng 18 ở app.js thành "hienthiBangGiaVe" |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context: Hiện tại mình đang gặp lỗi ở Tab Console hiển thị Uncaught ReferenceError: hienThiBangGia is not defined** 
- **Expected: Được sửa lỗi và hiển thị bảng giá** 
- **Actual:Không còn dòng đỏ xuất hiện trên Tab Console** 
- **Log: Hoàn thành** 

### Câu tìm kiếm Google

```text
site:stackoverflow.com "Uncaught ReferenceError: hienThiBangGia is not defined"
```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/ban_ve_thang_1.xlsx`, không cần ghi vào đây.
