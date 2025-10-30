# Digital Circut LAB02

## Đề bài
Cho F(A, B, C, D) = ∑(1,3,5,6,7,12,13,14)

	1. Vẽ mạch và khảo sát
	2. Rút gọn và vẽ mạch sử dụng NAND/NOR
	3. So sánh kết quả (1) và (2)


## Kết quả thực hành
### Vẽ mạch và khảo sát
F(A, B, C, D) = A’B’C’D + A’B’CD + A’BC’D + A’BCD’ + A’BCD + ABC’D’ + ABC’D + ABCD’

- Hình ảnh vẽ mạch và khảo sát Waveform trên ứng dụng Quartus:

    ![](https://media.discordapp.net/attachments/961544480366931969/1433361027449491608/image.png?ex=690468fb&is=6903177b&hm=36d9dfcc036925b675fbe6a4dbe5e61e44cfbb00fbef100ee785302a1064c56f&=&format=webp&quality=lossless&width=1119&height=855)

    ![](https://media.discordapp.net/attachments/961544480366931969/1433361049175851139/image.png?ex=69046900&is=69031780&hm=87321fccee0bbce27458e406fa3704e43d3d3fe9a2fc52f0e779f99c6044cd4a&=&format=webp&quality=lossless&width=1270&height=256)

### Rút gọn và vẽ lại mạch chỉ sử dụng cổng NAND
- Rút gọn hàm số:

    * F(A, B, C, D) = ∑(1,3,5,6,7,12,13,14)

    = A’B’C’D + A’B’CD + A’BC’D + A’BCD’ + A’BCD + ABC’D’ + ABC’D + ABCD’

    = (A’B’C’D + A’B’CD) + (A’BC’D + A’BCD) + (A’BCD’ + ABCD’) + (ABC’D’ +	ABC’D)

    = A’B’D + A’BD + BCD’ + ABC’

    = A’D + BCD’ + ABC’

    * Đặt X = A’D, Y = BCD’, Z = ABC’
        - X = A’D = (A’ NAND D)’
        - Y = BCD’ = (BC NAND D’)’ = [(B NAND C)’ NAND D’]’
        - Z = ABC’ = (AB NAND C’)’ = [(A NAND B)’ NAND C’]’
    * **F(A, B, C, D) = A’D + BCD’ + ABC’ = X + Y + Z = NAND(X’, Y’, Z’).**

- Hình ảnh vẽ mạch và khảo sát Waveform trên ứng dụng Quartus:

    ![](https://media.discordapp.net/attachments/961544480366931969/1433362431983489088/image.png?ex=69046a4a&is=690318ca&hm=de28ae163f8f2f8742fdf26b17dbcfa310fc66ce4ac98ba37836696fd82c7e1c&=&format=webp&quality=lossless&width=1191&height=586)

    ![](https://media.discordapp.net/attachments/961544480366931969/1433362473594916915/image.png?ex=69046a54&is=690318d4&hm=5f9c6897011c8a521f198bf7a08060b1791e7f8cb3c213c8acdd5daf586dc5da&=&format=webp&quality=lossless&width=1216&height=244)

### So sánh kết quả 2 mạch:
> *Ta xây dựng mạch so sánh kết quả của 2 mạch trên bằng cách input kết quả của 2 mạch qua cổng Logic XNOR2. Khi đó, nếu kết quả trả về 1 cho mọi trường hợp đầu vào, ta có thể kết luận kết quả của 2 mạch trên là trùng khớp.*
- Hình ảnh mạch so sánh dùng cổng Logic XNOR2 và Waveform khảo sát trên ứng dụng Quartus:

    ![](https://media.discordapp.net/attachments/961544480366931969/1433363152153739337/image.png?ex=69046af6&is=69031976&hm=8366a5313eda1289b3451055e83245cc25818ee7b85463aaa2dc7e8fa8251df2&=&format=webp&quality=lossless&width=1133&height=618)

    ![](https://media.discordapp.net/attachments/961544480366931969/1433363170147172416/image.png?ex=69046afa&is=6903197a&hm=5f35c6a7cdc20d36dc031799d48c4819ff2d66b950eecad258cf2b66ee181779&=&format=webp&quality=lossless&width=1194&height=186)

- Kết luận: 
    - So sánh kết quả của 2 mạch qua cổng XNOR tất cả đều cho ra kết quả bằng 1 (Kết quả của 2 mạch cho ra trùng nhau)
    - Đánh giá: Việc rút gọn mạch số mang lại những lợi ích thiết thực:
        - Giảm chi phí sản xuất: Ít linh kiện hơn: Mạch được rút gọn thường sử dụng ít cổng logic (gate) hơn, dẫn đến số transistor ít hơn. Trên một quy mô sản xuất hàng triệu chip, việc tiết kiệm dù chỉ một vài transistor cho mỗi chip cũng có thể tiết kiệm một khoản chi phí khổng lồ.
        - Kích thước chip nhỏ hơn: Diện tích silicon chiếm chỗ ít hơn, cho phép sản xuất nhiều chip hơn trên một tấm wafer.
        - Cải thiện hiệu suất: Mạch càng đơn giản, số tầng logic (logic level) giữa đầu vào và đầu ra càng ít. Điều này trực tiếp làm giảm độ trễ lan truyền (propagation delay), giúp mạch chạy ở tần số cao hơn.
        - Tiết kiệm năng lượng: Mạch đơn giản hơn đồng nghĩa với điện dung tải nhỏ hơn và ít cổng chuyển mạch hơn tại một thời điểm. Điều này dẫn đến mức tiêu thụ năng lượng (power consumption) thấp hơn, đặc biệt quan trọng đối với các thiết bị di động chạy bằng pin.
        - Tăng độ tin cậy: Mạch càng ít linh kiện thì xác suất hỏng hóc càng thấp. Ngoài ra, việc giảm độ phức tạp cũng giúp cho quá trình kiểm tra và gỡ lỗi (debug) dễ dàng hơn.
