# ⚙️ CHƯƠNG 2 – CÁC DẠNG BIỂU DIỄN SỐ
## Môn: Nhập môn Mạch số

---

## I. Tổng quan
- **Máy tính** sử dụng **hệ nhị phân (binary)** để biểu diễn và xử lý dữ liệu.  
- **Con người** thường dùng **hệ thập phân (decimal)**, nên cần **chuyển đổi giữa các hệ thống số**.  
- Ngoài ra còn có **hệ bát phân (octal)** và **thập lục phân (hexadecimal)** giúp biểu diễn gọn hơn.

---

## II. Các hệ thống số

| Hệ thống | Cơ số | Ký hiệu | Ví dụ | Ghi chú |
|-----------|--------|----------|--------|----------|
| **Thập phân** | 10 | 0–9 | 2745.214₁₀ | Dùng trong đời sống |
| **Nhị phân** | 2 | 0,1 | 1011.101₂ = 11.625₁₀ | Dùng trong máy tính |
| **Bát phân** | 8 | 0–7 | 372₈ = 250₁₀ | Gom 3 bit/nhóm |
| **Thập lục phân** | 16 | 0–9, A–F | 3BA₁₆ = 954₁₀ | Gom 4 bit/nhóm |

---

## III. Chuyển đổi giữa các hệ thống số

### 1. **Từ các hệ khác → Thập phân**
\[
N = \sum_{i=-m}^{n} d_i \times \text{base}^i
\]
Ví dụ:  
1A2F₁₆ = 1×16³ + 10×16² + 2×16¹ + 15×16⁰ = 6703₁₀

### 2. **Từ Thập phân → Nhị phân**
- Chia liên tiếp cho 2, ghi phần dư từ cuối lên đầu.  
- Dư đầu tiên → **LSB**, dư cuối → **MSB**.

**Ví dụ:**  
25₁₀ → 11001₂

### 3. **Từ Thập phân → Bát phân / Thập lục phân**
- Chia lần lượt cho 8 hoặc 16, ghi phần dư.  
Ví dụ:  
423₁₀ = 1A7₁₆

### 4. **Bát phân ↔ Nhị phân**
- Mỗi chữ số bát phân = **3 bit** nhị phân.  
Ví dụ:  
372₈ = 011 111 010₂ = 11111010₂

### 5. **Thập lục phân ↔ Nhị phân**
- Mỗi chữ số hex = **4 bit** nhị phân.  
Ví dụ:  
1F0C₁₆ = 0001 1111 0000 1100₂

### 6. **Bát phân ↔ Thập lục phân**
- Thực hiện qua **trung gian hệ nhị phân**.  
Ví dụ:  
1F0C₁₆ → 1111100001100₂ → 17414₈

---

## IV. Biểu diễn số phân số thập phân dưới dạng nhị phân
- Nhân phần **phân số** với 2, ghi phần nguyên mỗi bước.  
- Lặp lại cho đến khi phần phân số = 0 hoặc đạt độ chính xác mong muốn.

**Ví dụ:**  
0.625₁₀  
→ 0.625×2=1.25 → 1  
→ 0.25×2=0.5 → 0  
→ 0.5×2=1 → 1  
⟹ 0.625₁₀ = 0.101₂

---

## V. Các phép tính nhị phân **không dấu**

### 1. **Phép cộng**
| A | B | Tổng | Carry |
|---|---|------|--------|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

**Ví dụ:**  
```
  1011
+ 0010
------
  1101
```

### 2. **Phép nhân**
Giống phép nhân thông thường, nhưng chỉ có 0 và 1.  
Nếu bit = 1 → cộng dồn bản sao của số kia.

### 3. **Phép trừ**
Quy tắc mượn:
```
0−0=0   1−1=0   1−0=1   [1]0−1=1 (mượn 1)
```
Ví dụ: 10101₂ − 00111₂ = 01110₂

---

## VI. Biểu diễn số **có dấu**

### 1. **Bit dấu (sign bit)**
- 0 → dương  
- 1 → âm  
- Bit dấu nằm ở **ngoài cùng bên trái**.

### 2. **Ba cách biểu diễn số có dấu**
| Phương pháp | Cách biểu diễn | Ghi chú |
|--------------|----------------|----------|
| **Dấu và độ lớn** | 1 bit dấu + trị tuyệt đối | Gây lỗi khi cộng/trừ |
| **Bù 1 (One’s complement)** | Đảo tất cả bit của số dương | Có 2 biểu diễn cho 0 |
| **Bù 2 (Two’s complement)** | Đảo bit rồi +1 | Dùng trong máy tính hiện nay ✅ |

**Ví dụ:**  
Số 6 bit, biểu diễn ±52:  
+52 = 110100₂  
−52 (bù 2) = đảo bit +1 → 001100₂ + 1 = 001101₂

---

### 3. **Phép cộng/trừ với số bù 2**
- Cộng/trừ như số không dấu.  
- Bỏ bit nhớ cuối cùng.  
- Kết quả **luôn đúng**.

**Trừ bằng cộng:**  
A − B = A + (bù 2 của B)

### 4. **Hiện tượng tràn số học (Overflow)**
- Xảy ra khi kết quả vượt quá khoảng biểu diễn:  
\[-2^{n-1} \leq N \leq 2^{n-1}-1\]
- Tràn xảy ra **khi cộng hai số cùng dấu**, nhưng kết quả khác dấu.  
- Có mạch riêng để phát hiện overflow.

---

## VII. Các loại biểu diễn đặc biệt

### 1. **BCD (Binary Coded Decimal)**
- Mỗi chữ số thập phân (0–9) → 4 bit nhị phân.  
- Dễ hiển thị, chuyển đổi, nhưng tốn bộ nhớ.

**Ví dụ:**  
137₁₀ = `0001 0011 0111` (BCD)

### 2. **Số dấu chấm động (Floating-point – IEEE 754)**
Biểu diễn theo công thức:
\[
\text{Giá trị} = (-1)^{sign} \times (1.mantissa) \times 2^{(exponent - bias)}
\]

| Thành phần | Số bit (chuẩn 32-bit) |
|-------------|------------------------|
| Sign | 1 |
| Exponent (biased +127) | 8 |
| Fraction (Mantissa) | 23 |

**Ví dụ:**  
Số –157.625₁₀ ⇄ 01001101001110000000000000000000₂

### 3. **ASCII (American Standard Code for Information Interchange)**
- Chuẩn mã 7 bit (ASCII-7), biểu diễn 128 ký tự.  
- Dùng để mã hóa chữ, số, ký hiệu bàn phím.  
- Ví dụ: ‘A’ = 65₁₀ = 1000001₂

---

## VIII. Tóm tắt chương
Sinh viên cần nắm:
1. Các hệ thống số: **nhị phân, bát phân, thập lục phân, thập phân**.  
2. Cách **chuyển đổi giữa các hệ**.  
3. Phép **cộng, trừ, nhân** trong nhị phân.  
4. Cách **biểu diễn số có dấu** (bù 1, bù 2).  
5. **Phát hiện overflow** trong phép toán.  
6. Biểu diễn **BCD, dấu chấm động, ASCII**.

---
