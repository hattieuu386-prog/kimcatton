# Kịch bản quay video test độ dày tôn (dùng cho bot Giang)

3 video: VIDEO_TON_04, VIDEO_TON_08, VIDEO_INOX. Mỗi video 8-15 giây, quay dọc 9:16.

## Quy tắc chung (cả 3 video)

- Quay liền 1 cảnh từ lúc đo đến lúc cắt xong, không cắt ghép. Khách cần thấy đúng tấm tôn vừa đo là tấm được cắt.
- Đo độ dày bằng thước kẹp, quay cận màn hình số hoặc vạch đo, giữ 2 giây.
- Thu rõ tiếng cắt. Nhạc nền (nếu có) để nhỏ hơn tiếng cắt.
- Lau sạch gỉ, bôi dầu mỏng lên lưỡi trước khi quay.
- Nền sạch, đủ sáng. Tay sạch hoặc đeo găng.
- Không ghi tên, không đặt sản phẩm của shop khác trong khung hình.

## Trình tự cảnh

| Giây | Hình ảnh | Chữ trên màn hình |
|---|---|---|
| 0-3 | Thước kẹp đo mép tôn, quay cận số đo | TÔN [loại] - [số đo] LY |
| 3-8 | Đặt tôn vào kìm, cắt 1 nhát, miếng tôn rơi ra | (không chữ, để tiếng cắt) |
| 8-12 | Quay cận mép cắt: thẳng, không ba via | Mép cắt thẳng, không nhai tôn |
| 12-15 | Quay cận lưỡi sau khi cắt: không mẻ | Lưỡi SKD11 liền khối, tôi nhiệt |

## Riêng từng video

- **VIDEO_TON_04**: tôn lạnh hoặc tôn màu 0.4 ly, loại phổ biến nhất ở nhà dân.
- **VIDEO_TON_08**: tôn 0.8 ly. Nên cắt 3 nhát liên tiếp để chứng minh không phải may mắn.
- **VIDEO_INOX**:
  - Cắt thử ngoài khung hình trước, từ mỏng tới dày, để tìm độ dày lớn nhất mà kìm cắt ngọt và lưỡi không mẻ.
  - Chỉ quay và quảng cáo ở mức độ dày đó. Điền con số vào chỗ [ĐỘ DÀY INOX ĐÃ TEST] trong instruction của bot.
  - Quyết định trước: cắt inox có nằm trong bảo hành lưỡi không. Nếu không, bot phải nói rõ.

## Sau khi quay

1. Đặt tên file đúng: `VIDEO_TON_04.mp4`, `VIDEO_TON_08.mp4`, `VIDEO_INOX.mp4`.
2. Gắn từng video vào instruction Botcake, ngay cạnh dòng tên video trong mục [THƯ VIỆN VIDEO].
3. Chưa có video nào thì xóa dòng đó và các câu nhắc tới nó trong instruction, để bot không hứa gửi video không có.
