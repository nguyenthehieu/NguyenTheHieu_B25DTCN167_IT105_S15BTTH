## **PHẦN 1 — Entity / Attribute / Khóa chính**

| Entity | Attribute cần lưu | Khóa chính (PK) |
| ----- | ----- | ----- |
| **LOP\_TAP** | MaLop, TenLop, HocPhi | **MaLop** |
| **HOI\_VIEN** | MaHoiVien, TenHoiVien, SoDienThoai | **MaHoiVien** |
| **HUAN\_LUYEN\_VIEN** | MaHLV, TenHLV | **MaHLV** |

## **PHẦN 2 — Quan hệ và Khóa ngoại**

| Cặp Entity | Loại quan hệ | Khóa ngoại / Bảng trung gian |
| ----- | ----- | ----- |
| **HUAN\_LUYEN\_VIEN — LOP\_TAP** | **1-N** | LOP\_TAP.MaHLV → HUAN\_LUYEN\_VIEN.MaHLV |
| **HOI\_VIEN — LOP\_TAP** | **N-N** | Bảng trung gian **DANG\_KY**: MaHoiVien, MaLop |

**PHẦN 3 — Xử lý lỗi chuẩn hóa**

| Lỗi ở mục 4 | Vi phạm dạng chuẩn | Tách thành bảng nào, gồm cột gì |
| ----- | ----- | ----- |
| **TenLop, HocPhi chỉ phụ thuộc MaLop** | **2NF** | LOP\_TAP(MaLop, TenLop, HocPhi) |
| **SoDienThoai phụ thuộc TenHoiVien** | **3NF** | HOI\_VIEN(MaHoiVien, TenHoiVien, SoDienThoai) |

