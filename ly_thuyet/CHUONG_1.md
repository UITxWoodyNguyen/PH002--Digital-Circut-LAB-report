# 🧠 CHƯƠNG 1 – GIỚI THIỆU TỔNG QUAN VỀ MẠCH SỐ

## I. Tổng quan về kỹ thuật số
- **Kỹ thuật số (Digital Technology)** xuất hiện phổ biến trong các thiết bị hiện nay: máy tính, điện thoại, máy ảnh, robot, truyền thông, v.v.  
- **Gordon Moore** (đồng sáng lập Intel, 1968) phát biểu **Định luật Moore (1965)**:  
  > “Số lượng transistor trên mạch tích hợp tăng gấp đôi sau khoảng **2 năm**.”
- Sự phát triển của công nghệ bán dẫn theo định luật Moore đã thúc đẩy sự nhỏ gọn, mạnh mẽ và rẻ hơn của vi mạch số.

---

## II. Hệ thống tương tự (Analog) và hệ thống số (Digital)

| Đặc điểm | Hệ thống tương tự (Analog) | Hệ thống số (Digital) |
|-----------|-----------------------------|------------------------|
| **Dạng tín hiệu** | Liên tục theo thời gian | Rời rạc theo thời gian |
| **Giá trị tín hiệu** | Vô hạn giá trị | Chỉ 0 hoặc 1 |
| **Ví dụ** | Khuếch đại âm thanh, cảm biến nhiệt độ | Máy tính, ổ đĩa, xử lý dữ liệu nhị phân |
| **Thiết bị chuyển đổi** | - | **ADC** (Analog → Digital) và **DAC** (Digital → Analog) |

**Ứng dụng:**  
- Nén âm thanh/ảnh/video (MP3, MP4, JPEG, PNG) là ví dụ của xử lý tín hiệu số.

---

## III. Đặc điểm của tín hiệu số

1. **Trạng thái điện áp:**
   - Mức **Cao (High): 2V – 5V**  
   - Mức **Thấp (Low): 0V – 0.8V**  
   - Mức **Không xác định (Invalid): 0.8V – 2V** → có thể gây lỗi mạch.

2. **Dạng sóng số (Digital waveform):**  
   - Biểu diễn sự thay đổi giữa mức cao và thấp.  
   - **Xung dương (Positive-going pulse):** từ Low → High.  
   - **Xung âm (Negative-going pulse):** từ High → Low.

3. **Giản đồ định thời (Timing diagram):**  
   - Mô tả quan hệ giữa nhiều dạng sóng theo thời gian.

4. **Truyền dữ liệu số:**  
   - **Nối tiếp (Serial):** từng bit theo thời gian.  
   - **Song song (Parallel):** nhiều bit cùng lúc.

---

## IV. Quy trình thiết kế mạch số (Digital Design Process)

1. **Xác định yêu cầu thiết kế**  
2. **Mô tả kỹ thuật:** sơ đồ khối, lưu đồ hoạt động  
3. **Thiết kế sơ đồ logic**  
4. **Mô phỏng kiểm tra**  
5. **Hiệu chỉnh, sửa lỗi**  
6. **Kiểm thử thực tế (thử nghiệm trên kit/board)**  
7. **Hoàn thiện sản phẩm**

**Phương pháp thiết kế:**
- **Truyền thống:** dựa vào mô hình toán học, phù hợp thiết kế nhỏ.  
- **Hiện đại (CAD – Computer-Aided Design):**  
  - Thiết kế bằng phần mềm, tự động hóa cao, dễ kiểm tra và mô phỏng.  
  - Phù hợp thiết kế phức tạp (FPGA, ASIC).

**Thiết bị hỗ trợ:**  
- **Logic Analyzer:** quan sát nhiều kênh tín hiệu số đồng thời, hiển thị dạng sóng và giá trị theo thời gian.

---

## V. Phân loại chip số

### 1. Theo tính năng
- **Standard chips:**  
  - Thực hiện chức năng cố định, ví dụ họ **74xx** (7400 – NAND, 7404 – INV,…).
- **Programmable Logic Devices (PLD) / FPGA:**  
  - Có thể lập trình để thay đổi chức năng logic.  
  - Sử dụng công cụ **CAD** để mô tả và nạp cấu hình.
- **ASIC (Application-Specific Integrated Circuit):**  
  - Chip chuyên dụng, tối ưu hiệu suất, tốc độ và tiêu thụ điện.  
  - Dùng cho sản phẩm thương mại, nhưng giá thành cao.

### 2. Theo mức độ tích hợp
| Loại | Số lượng cổng logic | Viết tắt |
|-------|---------------------|-----------|
| Small Scale Integration | 1–20 cổng | SSI |
| Medium Scale Integration | 20–200 cổng | MSI |
| Large Scale Integration | 200–1.000.000 cổng | LSI |
| Very Large Scale Integration | >1.000.000 cổng | VLSI |

---

## VI. Các thuật ngữ cơ bản

| Thuật ngữ | Ý nghĩa |
|------------|----------|
| **Analog** | Tín hiệu liên tục |
| **Digital** | Tín hiệu rời rạc |
| **Binary (Nhị phân)** | Hệ cơ số 2, chỉ có giá trị 0 hoặc 1 |
| **Bit** | Đơn vị nhỏ nhất của dữ liệu số (0 hoặc 1) |
| **Programmable Logic Chip (FPGA)** | Chip logic có thể lập trình được |
| **Fixed-function Logic Chip (ASIC, 74xx)** | Chip logic có chức năng cố định |

---

## VII. Kết luận chương
Sinh viên cần nắm được:
- Sự khác biệt giữa **tín hiệu tương tự** và **tín hiệu số**.  
- **Quy trình thiết kế mạch số** và vai trò của **CAD tools**.  
- **Phân loại chip số** và mức độ tích hợp (SSI → VLSI).  
- Ý nghĩa của **định luật Moore** trong sự phát triển công nghệ vi mạch.  
- Các **thuật ngữ cơ bản**: bit, digital, analog, FPGA, ASIC.
