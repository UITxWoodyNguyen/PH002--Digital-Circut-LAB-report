# 🔢 CHƯƠNG 4 – BÌA KARNAUGH
## Môn: Nhập môn Mạch số

---

## I. Tổng quan
- **Mục tiêu chương học:**
  - Biểu diễn giá trị ngõ ra của một biểu thức logic.
  - Thiết kế mạch logic từ biểu thức Boolean.
  - Tính **chi phí thiết kế** của mạch logic.
  - Đơn giản / tối ưu mạch logic để giảm **số cổng, diện tích, chi phí và thời gian xử lý.**

---

## II. Các dạng biểu diễn biểu thức logic

### 1. Khái niệm Tích chuẩn và Tổng chuẩn
- **Tích chuẩn (Minterm):** là các tích (AND) mà **tất cả các biến** xuất hiện **ở dạng gốc hoặc phủ định**.  
  → Hàm Boolean có giá trị **1** tại tổ hợp tương ứng.  
- **Tổng chuẩn (Maxterm):** là các tổng (OR) mà **tất cả các biến** xuất hiện **ở dạng gốc hoặc phủ định**.  
  → Hàm Boolean có giá trị **0** tại tổ hợp tương ứng.

---

### 2. Dạng chính tắc (Canonical Form)
- **Dạng chính tắc 1 (SOP – Sum of Products):** Tổng các tích chuẩn có giá trị 1.  
  `F(A,B,C) = Σ(2,3,5)`
- **Dạng chính tắc 2 (POS – Product of Sums):** Tích các tổng chuẩn có giá trị 0.  
  `F(A,B,C) = Π(1,4,6)`
- **Trường hợp “don’t care” (D):**
  - Biểu diễn bằng `d()` hoặc `D()`
  - Dùng để **tối ưu hóa mạch** khi giá trị của một số tổ hợp không ảnh hưởng đến đầu ra.

---

### 3. Dạng chuẩn (Standard Form)
- Là dạng **đơn giản hóa** từ dạng chính tắc.  
- Có thể gồm ít nhóm AND/OR hơn hoặc ít biến hơn.
- Hai dạng cơ bản:
  - **Tổng của các tích (SoP):** `F = XY’Z + X’YZ + ...`
  - **Tích của các tổng (PoS):** `F = (X+Y’+Z)(X’+Y+Z)`

**Chuyển đổi giữa hai dạng:**
- SoP → Chính tắc: thêm `(v + v')` vào mỗi nhóm.  
- PoS → Chính tắc: thêm `vv'` vào mỗi nhóm.

---

## III. Thiết kế mạch logic số

### Quy trình thiết kế
1. **Bước 1:** Lập bảng chân trị (truth table).  
2. **Bước 2:** Viết biểu thức logic (SOP hoặc POS).  
3. **Bước 3:** Đơn giản biểu thức bằng đại số Boolean hoặc bìa Karnaugh.  
4. **Bước 4:** Vẽ sơ đồ mạch logic tương ứng.

### Tiêu chí đánh giá
- **Chi phí thiết kế (Cost):**
  - Phụ thuộc vào **số cổng logic** và **số ngõ vào của mỗi cổng.**
  - Chi phí được ước lượng theo công thức:
    - `C(B) = Σ Pj(B)`  
      Trong đó:  
      - `Pj(B)` = số biến trong thành phần thứ j  
      - `K` = số nhóm tích (SoP) hoặc tổng (PoS)

---

## IV. Bìa Karnaugh (Karnaugh Map)

### 1. Khái niệm
- Do **Maurice Karnaugh (1953)** đề xuất.  
- Là công cụ **hình học trực quan** giúp **rút gọn biểu thức logic.**
- Biểu diễn bảng chân trị dưới dạng **ma trận các ô (cells)**.  
- Mỗi ô tương ứng với **một tổ hợp ngõ vào** → **một minterm (hoặc maxterm).**

**Số ô trên bìa K-map:**  
- Với n biến → có **2ⁿ ô.**

---

### 2. Nguyên tắc vẽ bìa
- Hai ô liền kề chỉ khác nhau **1 bit.**
- Giá trị ngõ ra được điền vào các ô tương ứng.
- Dạng 2 biến, 3 biến, 4 biến, 5 biến.

---

## V. Phương pháp rút gọn bằng Bìa Karnaugh

### Các bước thực hiện:
1. **Vẽ bìa Karnaugh:** gồm 2ⁿ ô cho n biến.  
2. **Điền giá trị ngõ ra:**  
   - “1” nếu ngõ ra có giá trị 1 (SOP).  
   - “0” nếu ngõ ra có giá trị 0 (POS).
3. **Gom nhóm (Grouping):**  
   - Gom các ô liền kề có giá trị giống nhau.  
   - Mỗi nhóm có kích thước **2ⁱ ô** (1, 2, 4, 8, 16,...).  
   - Nhóm càng lớn càng tốt → giảm số biến trong biểu thức.  
   - Một ô có thể thuộc nhiều nhóm.
4. **Rút gọn biểu thức:**  
   - Nếu **gom theo minterm (SOP):**
     - Biến giữ nguyên nếu =1, đảo nếu =0.  
   - Nếu **gom theo maxterm (POS):**
     - Biến giữ nguyên nếu =0, đảo nếu =1.

---

### Ví dụ
- **3 biến:** `F = x’z + xy + yz`  
  → Rút gọn thành `F = x’z + xy`
- **4 biến:** `F = ac + a’b + d’`
- **5 biến:** `F = BE + B’CE’ + B’C’D’ + AB’D’ + ACDE’`

---

## VI. Biểu thức mang giá trị tùy định (Don't Care)

### 1. Khái niệm
- Một số tổ hợp ngõ vào **không xảy ra trong thực tế**, gọi là **don’t care** (ký hiệu X hoặc d).  
- Các ô này **có thể được xem là 1 hoặc 0** tùy theo cách đơn giản hóa:
  - **Nếu SoP:** xem X là **1.**
  - **Nếu PoS:** xem X là **0.**

### 2. Ứng dụng
- Dùng để **mở rộng nhóm** khi rút gọn K-map → giúp biểu thức ngắn hơn.

**Ví dụ:**  
Giả sử `F(0,0,1)` và `F(1,1,0)` không xác định → có thể chọn giá trị sao cho biểu thức đơn giản nhất.

---

## VII. Tóm tắt chương

Sinh viên cần nắm:
1. Các **dạng biểu diễn logic:** Chính tắc, Chuẩn, SoP, PoS.  
2. **Quy trình thiết kế mạch logic số.**
3. Cách **tính chi phí thiết kế.**
4. **Nguyên tắc và phương pháp rút gọn bằng bìa Karnaugh.**
5. Rút gọn K-map với **2, 3, 4, và 5 biến.**
6. Cách xử lý **giá trị tùy định (don’t care).**

---
