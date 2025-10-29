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
![](https://media.discordapp.net/attachments/961544480366931969/1433095859477811271/image.png?ex=69037206&is=69022086&hm=ff4eb5d14deb7831798d560f9755d2e61ea64e898a8ee3e30300c2073aebf1ed&=&format=webp&quality=lossless&width=1108&height=550)

![](https://media.discordapp.net/attachments/961544480366931969/1433095901462921297/image.png?ex=69037210&is=69022090&hm=85c8c34286b1ca95f97e70b4af37c5568c1e93ddc2c7f75e74303ac3f65da972&=&format=webp&quality=lossless&width=1126&height=446)

- Nhận xét:
    - Cổng AND cho ra tín hiệu "1" (TRUE) chỉ khi tất cả các đầu vào đều là "1". Nếu một hoặc nhiều đầu vào là "0", đầu ra sẽ là "0". (Đúng với bảng sự thật)
    - Cổng OR cho ra tín hiệu "1" khi ít nhất một trong các đầu vào là "1". Nếu tất cả các đầu vào đều là "0", đầu ra mới là "0".S (Đúng với bảng sự thật)
    - Cổng NOT chỉ có một đầu vào và nó đảo ngược trạng thái của tín hiệu đầu vào. Nếu đầu vào là “1”, đầu ra sẽ là “0” và ngược lại. (Đúng với bảng sự thật)

### Khảo sát hàm số F(A, B, C)
> **Ta có hàm số F(A, B, C) = A'BC + A'B'C + ABC**
- Dễ dàng lập được bảng giá trị sau:
# Bảng giá trị

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
![](https://media.discordapp.net/attachments/961544480366931969/1433096994578239560/image.png?ex=69037315&is=69022195&hm=e4913f59ed25e154c026136a1c97a34c77b663821428f1a567997e0a5aaf493f&=&format=webp&quality=lossless&width=1118&height=356)

![](https://media.discordapp.net/attachments/961544480366931969/1433097013964308581/image.png?ex=69037319&is=69022199&hm=ff47b069406472cbee2bf31a1e275f23dc3d69308bc9f171c754067403ddfb4d&=&format=webp&quality=lossless&width=1116&height=369)

- Nhận xét:
    - Dựa vào bảng giá trị, ta có:
        - F = 1 khi (A,B,C) = (0,0,1), (0,1,1), (1,1,1).
        - F = 0 ở các trường hợp còn lại.
    - Khi C = 0, hàm luôn bằng 0 → C là điều kiện bắt buộc để F = 1.
    - Khi C = 1, giá trị của F phụ thuộc vào A và B:
        - Nếu B = 1, F luôn = 1 bất kể A là 0 hay 1.
        - Nếu B = 0, F = 1 chỉ khi A = 0.
    - Hay nói cách khác, hàm chỉ bằng 1 khi C = 1 và (A = 0 hoặc B = 1).
