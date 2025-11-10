# Digital Circut LAB01

## Đề bài
1. Khảo sát cổng Logic: AND, OR, NOT
2. Khảo sát mạch số: F(A,B,C) = A'BC + A'B'C + ABC

## Kết quả thực hành
### Khảo sát cổng Logic AND, OR, NOT
- Với 2 input A, B, ta lập được bảng giá trị sau:
  
| A | B | A AND B | A OR B | NOT A |
|---|---|----------|--------|-------|
| 0 | 0 | 0 | 0 | 1 |
| 0 | 1 | 0 | 1 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 1 | 1 | 1 | 0 |
- Mạch vẽ và Waveform khảo sát trên Quartus:
  
  ![](https://github.com/UITxWoodyNguyen/PH002--Digital-Circut-LAB-report/blob/main/%5BDIGI%5D%20LAB_01/image_1.png)

  ![](https://github.com/UITxWoodyNguyen/PH002--Digital-Circut-LAB-report/blob/main/%5BDIGI%5D%20LAB_01/image_2.png)

- Nhận xét:
    - Cổng AND cho ra tín hiệu "1" (TRUE) chỉ khi tất cả các đầu vào đều là "1". Nếu một hoặc nhiều đầu vào là "0", đầu ra sẽ là "0". (Đúng với bảng sự thật)
    - Cổng OR cho ra tín hiệu "1" khi ít nhất một trong các đầu vào là "1". Nếu tất cả các đầu vào đều là "0", đầu ra mới là "0".S (Đúng với bảng sự thật)
    - Cổng NOT chỉ có một đầu vào và nó đảo ngược trạng thái của tín hiệu đầu vào. Nếu đầu vào là “1”, đầu ra sẽ là “0” và ngược lại. (Đúng với bảng sự thật)

### Khảo sát hàm số F(A, B, C)
> **Ta có hàm số F(A, B, C) = A'BC + A'B'C + ABC**
- Dễ dàng lập được bảng giá trị sau:

| A | B | C | A'BC | A'B'C | ABC | F(A,B,C) |
|---|---|---|------|-------|-----|----------|
| 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 0 | 1 | 0 | 1 |
| 0 | 1 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 1 | 0 | 0 | 1 |
| 1 | 0 | 0 | 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 0 | 0 | 0 | 0 |
| 1 | 1 | 0 | 0 | 0 | 0 | 0 |
| 1 | 1 | 1 | 0 | 0 | 1 | 1 |
- Mạch vẽ và Waveform khảo sát:
  
  ![](https://github.com/UITxWoodyNguyen/PH002--Digital-Circut-LAB-report/blob/main/%5BDIGI%5D%20LAB_01/image_3.png)

  ![](https://github.com/UITxWoodyNguyen/PH002--Digital-Circut-LAB-report/blob/main/%5BDIGI%5D%20LAB_01/image_4.png)

- Nhận xét:
    - Dựa vào bảng giá trị, ta có:
        - F = 1 khi (A,B,C) = (0,0,1), (0,1,1), (1,1,1).
        - F = 0 ở các trường hợp còn lại.
    - Khi C = 0, hàm luôn bằng 0 → C là điều kiện bắt buộc để F = 1.
    - Khi C = 1, giá trị của F phụ thuộc vào A và B:
        - Nếu B = 1, F luôn = 1 bất kể A là 0 hay 1.
        - Nếu B = 0, F = 1 chỉ khi A = 0.
    - Hay nói cách khác, hàm chỉ bằng 1 khi C = 1 và (A = 0 hoặc B = 1).
