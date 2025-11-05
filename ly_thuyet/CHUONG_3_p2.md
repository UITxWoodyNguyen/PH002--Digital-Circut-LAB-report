# Chương 3: Đại Số Boolean và Các Cổng Logic (Tiếp theo)

## Nội dung chính

1. **Tổng quan**
2. **Các cổng logic cơ bản**
   - AND, OR, NOT
   - NAND, NOR
   - XOR, XNOR
3. **Thiết kế mạch số từ biểu thức logic**
4. **Xác định biểu thức logic của một mạch số**
5. **Phân tích giá trị ngõ ra của một mạch số**
6. **Đại số Boolean**

---

## Phân tích giá trị ngõ ra của mạch logic

**Quy trình 5 bước:**

1. **Lập bảng sự thật** - Liệt kê tất cả các input có trong mạch tổ hợp
2. **Tạo cột cho các tín hiệu trung gian (node)** - Mỗi node là một tín hiệu giữa các cổng
3. **Điền giá trị cho các node** - Dựa trên hoạt động của cổng logic
4. **Dự đoán giá trị node cuối cùng** - Xác định output của cổng cuối cùng
5. **Kết hợp các cột node** - Để xác định giá trị ngõ ra cuối cùng

---

## Đại số Boolean

- Mạch số được xây dựng dựa trên biểu thức Boolean
- Biểu thức càng đơn giản → mạch càng nhỏ, rẻ, ít tốn năng lượng, nhanh hơn
- Sử dụng **định luật Boolean** để đơn giản hóa biểu thức

---

## Các định luật Boolean

### Định luật Boolean I (AND)
- Nếu một ngõ vào AND bằng 0 → ngõ ra = 0
- Nếu một ngõ vào AND bằng 1 → ngõ ra bằng giá trị ngõ vào còn lại
- `x · x = x`

### Định luật Boolean II (OR)
- Nếu một ngõ vào OR bằng 1 → ngõ ra = 1

### Định luật Boolean III (Phân phối)
- `x + yz = (x + y)(x + z)`

### Định luật Boolean IV (Đa biến)
- Một số định luật không có trong đại số thông thường

### Định luật Boolean V (Đối ngẫu)
- Thay AND bằng OR, OR bằng AND, 0 thành 1, 1 thành 0
- Ví dụ:
  - `1 + 1 = 1` → đối ngẫu: `0 · 0 = 0`
  - `1 + 0 = 1` → đối ngẫu: `0 · 1 = 0`

---

## Định luật DeMorgan

- Dùng để đơn giản hóa biểu thức có phép đảo
- Công thức:
  - `A · B = A + B`
  - `A + B = A · B`

### Ứng dụng DeMorgan để chuyển đổi cổng:
- AND ↔ NOR
- OR ↔ NAND

**Các bước thực hiện:**
1. Nghịch đảo tất cả input và output
2. Thêm dấu bù (bong bóng) tại ngõ vào/ra chưa có
3. Xóa dấu bù tại ngõ vào/ra đã có

---

## Ví dụ áp dụng

- **Ví dụ 1:** Đơn giản biểu thức Boolean sử dụng định luật
- **Ví dụ 2:** Áp dụng DeMorgan để chuyển đổi cổng logic

---

## Tóm tắt chương

Sau khi học xong chương này, sinh viên cần nắm:
- Phương pháp phân tích giá trị ngõ ra của mạch số
- Các định luật Boolean
- Ứng dụng định luật Boolean để tối ưu hóa thiết kế mạch số

---

*Tài liệu được tóm tắt từ bài giảng "Buổi 5_Chương 3_Đại số Boolean và các cổng Logic (tt)" - UIT-CE, 2016.*
