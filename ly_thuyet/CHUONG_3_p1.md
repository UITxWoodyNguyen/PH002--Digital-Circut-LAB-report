# 🔢 CHƯƠNG 3 – ĐẠI SỐ BOOLEAN VÀ CÁC CỔNG LOGIC
## Môn: Nhập môn Mạch số

---

## I. Tổng quan

- **Đại số Boolean** chỉ làm việc với **hai giá trị logic: 0 và 1**  
  → Tương ứng với hai trạng thái **OFF / ON** trong mạch điện tử.  
- Là nền tảng cho việc **phân tích, thiết kế và tối ưu mạch số**.  
- Các cổng logic cơ bản: **OR, AND, NOT, NOR, NAND, XOR, XNOR**.  
- **Bảng chân trị (Truth Table)** thể hiện mối quan hệ giữa **ngõ vào** và **ngõ ra** của một mạch.

| Số ngõ vào | Số dòng trong bảng |
|-------------|--------------------|
| 2 inputs | 2² = 4 |
| 3 inputs | 2³ = 8 |

---

## II. Các cổng logic cơ bản

### 1. Cổng OR (Tổng logic)
- Biểu thức: `X = A + B`
- **Ký hiệu `+`** không phải phép cộng thông thường.  
- **Ngõ ra = 1** khi **ít nhất một ngõ vào = 1**.

| A | B | X = A + B |
|---|---|-----------|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

---

### 2. Cổng AND (Tích logic)
- Biểu thức: `X = A ⋅ B`
- **Ngõ ra = 1** khi **tất cả ngõ vào = 1**.

| A | B | X = A⋅B |
|---|---|----------|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

---

### 3. Cổng NOT (Phủ định / Nghịch đảo)
- Biểu thức: `X = ¬A = A'`
- **Có duy nhất 1 ngõ vào**.
- **Ngõ ra đối nghịch với ngõ vào**.

| A | X = ¬A |
|---|---------|
| 0 | 1 |
| 1 | 0 |

> Cổng NOT còn gọi là **Inverter** – cổng đảo tín hiệu.

---

### 4. So sánh: OR – AND – NOT
- **OR:** Chỉ cần *một* input 1 → Output 1  
- **AND:** Cần *tất cả* input 1 → Output 1  
- **NOT:** Đảo giá trị logic

---

## III. Các cổng logic mở rộng

### 1. Cổng NOR (NOT + OR)
- Biểu thức: `X = ¬(A + B)`
- Ngõ ra chỉ **bằng 1 khi tất cả input = 0**.
- Cổng NOR là **hàm đầy đủ**: có thể thay thế cho OR, AND, NOT.

| A | B | X |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 0 |

> **Chip NOR:** 74LS02

---

### 2. Cổng NAND (NOT + AND)
- Biểu thức: `X = ¬(A ⋅ B)`
- Ngõ ra **bằng 0 khi tất cả input = 1**.  
- Cổng NAND cũng là **hàm đầy đủ**, có thể thay thế toàn bộ các cổng khác.

| A | B | X |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

> **Chip NAND:** 74LS00

---

### 3. Cổng XOR (Exclusive OR)
- Biểu thức: `X = A ⊕ B`
- **Ngõ ra = 1 khi số ngõ vào 1 là lẻ**.

| A | B | X = A⊕B |
|---|---|----------|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

---

### 4. Cổng XNOR (Exclusive NOR)
- Biểu thức: `X = ¬(A ⊕ B)` hoặc `A ⊙ B`
- **Ngõ ra = 1 khi số ngõ vào 1 là chẵn**.

| A | B | X = A⊙B |
|---|---|----------|
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

---

## IV. Thiết kế mạch số từ biểu thức logic

### 1. Nguyên tắc
- Chỉ sử dụng **các cổng logic cơ bản** (AND, OR, NOT).  
- Hoặc thiết kế tương đương chỉ với **NOR** hoặc **NAND**.  
- Nếu đề không giới hạn số ngõ vào → người thiết kế có thể chọn tùy ý.

### 2. Thứ tự ưu tiên trong biểu thức logic
1. **NOT** (phủ định)  
2. **AND** (tích logic)  
3. **OR** (tổng logic)  
> Dấu ngoặc `()` có ưu tiên cao nhất.

**Ví dụ:**  
`X = A + B⋅C`  
→ Thực hiện `B⋅C` trước, sau đó cộng OR với `A`.

---

## V. Xác định biểu thức logic từ mạch
- Phân tích mạch bằng cách đi từ **input → output**,  
  đọc theo các **cổng logic nối tiếp**.
- **Cổng đảo (Inverter)** sẽ biến A → A’.

---

## VI. Đại số Boolean

### 1. Tập giá trị và phép toán
- Tập giá trị: `{0, 1}`  
- Các phép cơ bản:
  - **Phủ định:** A’  
  - **Tổng:** A + B  
  - **Tích:** A⋅B

### 2. Một số định luật cơ bản

| Tên định luật | Biểu thức |
|---------------|------------|
| Luật giao hoán | A + B = B + A ; A⋅B = B⋅A |
| Luật kết hợp | (A + B) + C = A + (B + C) |
| Luật phân phối | A⋅(B + C) = A⋅B + A⋅C |
| Luật bù | A + A’ = 1 ; A⋅A’ = 0 |
| Luật lũy đẳng | A + A = A ; A⋅A = A |
| Luật 0 và 1 | A + 0 = A ; A + 1 = 1 ; A⋅0 = 0 ; A⋅1 = A |
| Luật De Morgan | (A + B)’ = A’⋅B’ ; (A⋅B)’ = A’ + B’ |

---

## VII. Ứng dụng và ý nghĩa
- Các **cổng logic** là **thành phần cơ bản** của mọi hệ thống kỹ thuật số.  
- Là cơ sở để thiết kế các **mạch tổ hợp**, **mạch tuần tự**, **CPU**, **bộ nhớ**, v.v.  
- Hiểu rõ các **định luật Boolean** giúp **tối giản mạch**, giảm số lượng cổng sử dụng.

---

## VIII. Tóm tắt chương
Sinh viên cần nắm:
1. Khái niệm **đại số Boolean** và **bảng chân trị**.  
2. Chức năng của các **cổng logic cơ bản và mở rộng**.  
3. Cách **biểu diễn và thiết kế mạch logic** từ biểu thức.  
4. Thứ tự ưu tiên và **cách xác định biểu thức từ mạch**.  
5. Các **định luật Boolean** và ứng dụng trong rút gọn mạch logic.

---
