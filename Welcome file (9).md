# Hoàng Xuân Nam 
### bài luyện tập 
---

pwd: hiển thị đường dẫn tuyệt đối


ls -Force:  Liệt kê nội dung, gồm cả file ẩn

Di chuyển cap_nhat.txt vào docs, file logo vào media:
 mv cap_nhat.txt docs/
 mv logo_gamezone.png media/

Sao chép logo từ media vào backup:
 cp media/logo_gamezone.png backup/

Xoá file .tmp ở gốc:
 rm temp_207.tmp

4.2: Dùng đường dẫn tương đối vào logs, liệt kê nội dung rồi quay lại gốc:
 cd logs
 ls
 cd ..
 Directory: C:\...\gamezone-website

Mode                 LastWriteTime         Length Name
----                 -------------         ------+ ----
d-----        10/26/2026   2:34 PM                backup
d-----        10/26/2026   2:34 PM                data
d-----        10/26/2026   2:34 PM                docs
d-----        10/26/2026   2:34 PM                logs
d-----        10/26/2026   2:34 PM                media
-a----        10/26/2026   2:34 PM             XX .env
-a----        10/26/2026   2:34 PM            XXX README.md
-a----        10/26/2026   2:34 PM            XXX bai_lam.md
4.3-   **Lệnh lọc (chạy trong terminal):**
    
    PowerShell
    
    ```
    Get-Content logs/game.log | Select-String "ERROR" > logs/daily_report.txt
    
    ```
    
-   **Lệnh kiểm tra và kết quả 2 dòng lỗi đầu tiên ghi vào `bai_lam.md`:**
    
    PowerShell
    
    ```
    Get-Content logs/daily_report.txt -TotalCount 2
    ```
    4.4: # Quản lý hệ thống web game GameZone

Đây là hệ thống **quản lý web game** được vận hành và _kiểm soát tự động_ bởi đội ngũ kỹ thuật.

## Thư mục dự án
| Thư mục / File | Nội dung mô tả |
| :--- | :--- |
| `docs/` | Tài liệu cập nhật hệ thống (`cap_nhat.txt`) |
| `media/` | Tài nguyên hình ảnh, logo của game |
| `logs/` | Lưu trữ file log và các báo cáo lỗi hệ thống |

## Lệnh liệt kê dự án
```powershell
ls -Recurse -Force
**Lệnh tạo file `logs/tong_hop.txt` chỉ dùng CLI:**

PowerShell

```
"=== TONG HOP LOG GAMEZONE ===" > logs/tong_hop.txt
Get-Content logs/game.log | Select-String "WARNING" >> logs/tong_hop.txt
(Get-Content logs/game.log | Select-String "ERROR" | Measure-Object).Count >> l
```
