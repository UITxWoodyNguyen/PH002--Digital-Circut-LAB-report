# 🔢 CHƯƠNG 3 – ĐẠI SỐ BOOLEAN VÀ CÁC CỔNG LOGIC
## Môn: Nhập môn Mạch số

---

## I. Tổng quan
- **Đại số Boolean** chỉ xử lý **hai giá trị logic 0 (OFF) và 1 (ON)**.  
- Là cơ sở của **mạch logic** trong máy tính, vi điều khiển và hệ thống số.  
- Các **cổng logic cơ bản**: OR, AND, NOT, NOR, NAND, XOR, XNOR.  
- **Bảng chân trị (truth table)** mô tả mối quan hệ giữa ngõ vào (inputs) và ngõ ra (outputs).  
  - 2 ngõ vào → 2² = 4 tổ hợp.
  - 3 ngõ vào → 2³ = 8 tổ hợp.

---

## II. Các cổng logic cơ bản

### 1. Cổng OR (Tổng logic)
- Biểu thức: `X = A + B`
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
- Cổng **INVERTER** có **1 ngõ vào**, **ngõ ra đảo ngược** ngõ vào.

| A | X = ¬A |
|---|---------|
| 0 | 1 |
| 1 | 0 |

---

## III. Các cổng logic mở rộng

### 1. Cổng NOR (NOT + OR)
- Biểu thức: `X = ¬(A + B)`
- **Ngõ ra = 1** khi **tất cả ngõ vào = 0**.  
- Có thể dùng **NOR** để tạo mọi cổng logic khác.  
- **Chip thông dụng:** 74LS02

| A | B | X |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 0 |

---

### 2. Cổng NAND (NOT + AND)
- Biểu thức: `X = ¬(A ⋅ B)`
- **Ngõ ra = 0** khi **tất cả ngõ vào = 1**.  
- Cổng **đa năng (Universal Gate)** – có thể thay thế OR, AND, NOT.  
- **Chip thông dụng:** 74LS00

| A | B | X |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

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

### Nguyên tắc thiết kế
1. Dựa vào **biểu thức Boolean** cho trước.  
2. Sử dụng **cổng OR, AND, NOT**, hoặc thay bằng **NOR / NAND**.  
3. Nếu không quy định số ngõ vào, có thể chọn tùy ý.  

**Thứ tự ưu tiên trong biểu thức:**
1. NOT (phủ định)  
2. AND (tích logic)  
3. OR (tổng logic)  
> Ngoặc `()` có ưu tiên cao nhất.

**Ví dụ:**  
`X = A + B⋅C` → thực hiện B⋅C trước, sau đó cộng OR với A.

---

## V. Xác định biểu thức logic từ mạch số
- Phân tích từ **ngõ vào → ngõ ra** theo các cổng nối tiếp.  
- Gặp cổng đảo thì thêm dấu `'` (phủ định).  
- Ví dụ: Input A qua inverter → output = A’.

---

## VI. Phân tích giá trị ngõ ra của mạch logic

### Quy trình phân tích
1. **Lập bảng chân trị** – liệt kê tất cả các input.  
2. **Tạo cột trung gian (node)** cho từng tín hiệu trong mạch.  
3. **Tính giá trị từng node** theo thứ tự hoạt động.  
4. **Kết hợp logic các node** để tính **output cuối cùng**.

→ Giúp kiểm tra mạch hoạt động đúng với biểu thức hay không.

---

## VII. Đại số Boolean

### 1. Ý nghĩa
- Dùng để **mô tả mạch logic** bằng biểu thức toán học.  
- Mạch càng đơn giản → chi phí, công suất, thời gian xử lý càng nhỏ.

### 2. Các định luật cơ bản

| Nhóm định luật | Biểu thức | Giải thích |
|----------------|------------|-------------|
| **Luật AND** | 0⋅x=0 ; 1⋅x=x ; x⋅x=x | Nếu 1 input là 0 → output 0 |
| **Luật OR** | 1+x=1 ; 0+x=x ; x+x=x | Nếu 1 input là 1 → output 1 |
| **Luật phân phối** | x + yz = (x+y)(x+z) | Phân phối tổng và tích |
| **Luật bù** | x+x’=1 ; x⋅x’=0 | Một biến và phủ định của nó |
| **Luật De Morgan** | (A+B)’=A’⋅B’ ; (A⋅B)’=A’+B’ | Đảo dấu, đổi phép toán |
| **Tính đối ngẫu (Duality)** | Đổi AND↔OR, 0↔1 | Hai biểu thức tương đương khi đổi vai trò toán tử |

---

### 3. Ứng dụng định luật De Morgan
- Cho phép **chuyển đổi giữa AND↔NOR** và **OR↔NAND**.  
- Quy tắc:  
  - Đảo **tất cả input và output**.  
  - Thêm/bỏ **dấu bù (bong bóng)** tương ứng trên sơ đồ.

**Ví dụ:**  
(A + B)’ = A’⋅B’ ⇄ cổng NOR tương đương hai cổng NOT + AND.

---

### 4. Ví dụ rút gọn biểu thức
**Ví dụ:**  
F = (A+B)’C + A(B+C)’  
→ Dùng DeMorgan và phân phối → biểu thức tối giản.

---

## VIII. Tóm tắt chương

Sinh viên cần nắm:
1. Khái niệm **đại số Boolean** và **bảng chân trị**.  
2. Hoạt động của **7 cổng logic cơ bản**.  
3. Cách **thiết kế mạch từ biểu thức logic** và ngược lại.  
4. Phương pháp **phân tích ngõ ra mạch logic**.  
5. **Định luật Boolean**, **DeMorgan**, **đối ngẫu** và **rút gọn biểu thức**.  
6. Ứng dụng các định luật để **tối ưu mạch logic**.

---
