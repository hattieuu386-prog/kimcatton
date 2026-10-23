# Kịch bản quay video test độ dày tôn (dùng cho bot Giang)

3 video: VIDEO_TON_05_06 (video chính), VIDEO_TON_08, VIDEO_INOX. Mỗi video 12-20 giây, quay dọc 9:16.

Đơn vị trên màn hình dùng "zem" cho quen tai thợ, kèm ly trong ngoặc. Ví dụ: 6 ZEM (0.6 LY).

## Mục tiêu: khách phải thấy 2 khác biệt

1. **Lưỡi khác**: 1 khối thép SKD11 nguyên tấm, cắt dây, tôi nhiệt. Phần lưỡi cắt không phải nhiều miếng ghép.
2. **Đường cắt khác**: mép thẳng, góc sóng sắc nét, miếng ốp úp lên sóng khít, không hở, nên chống hắt mưa.

Không cần đưa sản phẩm của shop khác vào. Khách tự so với kìm họ đang thấy ở nơi khác.

## Quy tắc chung

- Quay liền 1 cảnh từ lúc đo đến lúc cắt xong, không cắt ghép. Khách cần thấy đúng tấm tôn vừa đo là tấm được cắt.
- Đo bằng thước kẹp, quay cận số đo, giữ 2 giây.
- Thu rõ tiếng cắt. Nhạc nền (nếu có) nhỏ hơn tiếng cắt.
- Lau sạch gỉ, bôi dầu mỏng lên lưỡi trước khi quay.
- Dùng tôn mới, mặt sơn không xước, để vết xước không bị hiểu là do kìm.
- Nền sạch, đủ sáng. Tay sạch hoặc đeo găng.
- Không ghi tên, không đặt sản phẩm của shop khác trong khung hình.

## VIDEO_TON_05_06 (video chính: tôn sối, ốp nóc 5-6 zem)

| Giây | Hình ảnh | Chữ trên màn hình |
|---|---|---|
| 0-3 | Tháo lưỡi ra, cầm trên tay, xoay cho thấy 1 khối liền. Quay cận mặt đầu có vạch cắt dây | LƯỠI 1 KHỐI SKD11 - CẮT DÂY - TÔI NHIỆT |
| 3-6 | Thước kẹp đo mép tôn, quay cận số đo | TÔN SỐI 6 ZEM (0.6 LY) |
| 6-10 | Đặt tôn vào kìm, cắt 1 nhát, miếng tôn rơi ra | (không chữ, để tiếng cắt) |
| 10-14 | Quay cận mép cắt và góc sóng: thẳng, sắc, không ba via, sơn không bong | Mép thẳng, không nhai tôn |
| 14-20 | Úp tấm vừa cắt lên tấm tôn sóng, quay ngang tầm mắt cho thấy không có khe hở | Úp khít sóng, chống hắt mưa |

Cảnh 14-20 là bằng chứng khác biệt mạnh nhất: lưỡi lệch hoặc ghép sẽ cho đường cắt lệch, úp lên sẽ hở. Nếu được, chiếu đèn pin từ phía sau mối úp để thấy ánh sáng không lọt qua.

## VIDEO_TON_08 (tôn 8 zem, chứng minh kìm dư sức)

| Giây | Hình ảnh | Chữ trên màn hình |
|---|---|---|
| 0-3 | Thước kẹp đo, quay cận số đo | TÔN 8 ZEM (0.8 LY) |
| 3-12 | Cắt 3 nhát liên tiếp trên cùng tấm | (không chữ, để tiếng cắt) |
| 12-16 | Quay cận 3 mép cắt đặt cạnh nhau: đều nhau | 3 nhát như 1 |
| 16-20 | Quay cận lưỡi sau khi cắt: không mẻ, không lệch | Lưỡi liền khối, cắt lâu không lệch |

## VIDEO_INOX

- Cắt thử ngoài khung hình trước, từ mỏng tới dày, tìm độ dày lớn nhất mà kìm cắt ngọt và lưỡi không mẻ.
- Chỉ quay và quảng cáo ở mức độ dày đó. Điền con số vào chỗ [ĐỘ DÀY INOX ĐÃ TEST] trong instruction của bot.
- Quyết định trước: cắt inox có nằm trong bảo hành lưỡi không. Nếu không, bot phải nói rõ.
- Trình tự cảnh giống VIDEO_TON_08: đo, cắt, quay cận mép, quay cận lưỡi.

## Sau khi quay

1. Đặt tên file đúng: `VIDEO_TON_05_06.mp4`, `VIDEO_TON_08.mp4`, `VIDEO_INOX.mp4`.
2. Gắn từng video vào instruction Botcake, ngay cạnh dòng tên video trong mục [THƯ VIỆN VIDEO].
3. Chưa có video nào thì xóa dòng đó và các câu nhắc tới nó trong instruction, để bot không hứa gửi video không có.
4. Cảnh 0-3 giây của VIDEO_TON_05_06 (lưỡi 1 khối) và cảnh úp khít sóng nên cắt riêng ra dùng làm mở đầu cho video quảng cáo.
