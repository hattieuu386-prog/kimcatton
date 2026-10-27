# Kịch bản Luồng tin nhắn Botcake (khớp với instruction AI "chăm kìm")

Nguyên tắc: luồng lo tin đầu tiên và nút chọn kìm. AI lo mọi tin khách tự gõ sau đó.
Giá, quà, câu hỏi chọn kìm trong luồng phải giống hệt instruction AI. Sửa một bên thì sửa cả bên kia.

---

## LUỒNG 0: tin mở đầu cho quảng cáo (gắn vào Payload JSON)

Tin này hiện sẵn trong khung chat ngay khi khách bấm quảng cáo, TRƯỚC khi khách nhắn gì.
Meta chỉ cho 1 tin, gồm 1 ảnh hoặc chữ, kèm nút trả lời nhanh. Không gửi được nhiều ảnh, video liên tiếp.
Vì vậy: tin này phải tự đủ (có giá + quà), nút bấm mới mở phần còn lại.

Làm trong Botcake: Luồng tin nhắn -> Opt-in Message (hoặc luồng có nút "Chia sẻ Payload"), rồi lấy JSON dán vào mẫu tin nhắn của quảng cáo.

**Ảnh (1 ảnh):** lưỡi SKD11 nguyên khối, hoặc miếng tôn cắt úp khít sóng. Ảnh thật.

**Chữ:**
```
Kìm cắt tôn ốp sóng KMS 1tr599k, miễn ship 🛠️
🎁 Tặng 2 đôi găng tay chống cắt
Lưỡi 1 miếng SKD11 nguyên khối, nhận hàng cắt thử rồi mới trả tiền.
Anh lấy loại nào ạ? 👇
```

**3 nút trả lời nhanh** (tiêu đề tối đa 20 ký tự):

| Tiêu đề nút | Bấm vào thì | Hành động thêm |
|---|---|---|
| Dân Dụng 3 trong 1 | Gửi tin nhắn -> khối "Tư vấn dân dụng" | Bật Bot + Gắn nhãn `kim-dan-dung` |
| Công Nghiệp 5 Sóng | Gửi tin nhắn -> khối "Tư vấn công nghiệp" | Bật Bot + Gắn nhãn `kim-cong-nghiep` |
| Xem video cắt thử | Gửi luồng "chào báo giá" (Luồng 1: ảnh, video, giá, nút chọn kìm) | Bật Bot |

Khách không bấm nút mà tự gõ: AI trả lời. Bảng giá đã nằm trong lịch sử chat nên AI không gửi lại (BƯỚC 1 của instruction).

---

## LUỒNG 1: "chào báo giá"

**Điểm kích hoạt** (gắn cả 4):
- Payload JSON của quảng cáo (mỗi quảng cáo 1 bản sao luồng, đặt tên "chào – ads A", "chào – ads B"...)
- Tin nhắn mở đầu
- Câu hỏi thường gặp: "Xin giá kìm"
- Từ khoá: `xin giá kìm` (khớp chính xác nếu có tùy chọn)

**Loại tin nhắn:** Trong khoảng 24 giờ.

**Thứ tự khối trong "Nội dung" (từ trên xuống):**

1. **Hình ảnh** (Nhóm ảnh, 2 ảnh thật):
   - Ảnh lưỡi SKD11 nguyên khối
   - Ảnh miếng tôn cắt úp khít sóng
2. **Video**: video cắt tôn ngắn (dưới 15 giây). Nếu chưa có video ưng ý thì bỏ khối này.
3. **Đang nhập / chờ 2-3 giây** (nếu Botcake có khối này).
4. **Văn bản** (khối cuối cùng, gắn 3 nút):

```
💥 KÌM CẮT TÔN KMS - LƯỠI SKD11 NGUYÊN KHỐI, TÔI NHIỆT
🔥 1tr599k - MIỄN SHIP TOÀN QUỐC
🎁 Tặng 2 đôi găng tay chống cắt
🔧 Nhận hàng cắt thử rồi mới trả tiền, lỗi 1 đổi 1
Anh lấy kìm dân dụng 3 trong 1 (cắt tôn 6-9-11 sóng) hay kìm công nghiệp (tôn 5 sóng) ạ? 👇
```

**3 nút (Thêm nút) gắn vào khối văn bản:**

| Tiêu đề nút | Hành động khi nhấn nút | Hành động thêm |
|---|---|---|
| Dân Dụng 3 trong 1 | Gửi tin nhắn -> khối "Tư vấn dân dụng" | Bật Bot + Gắn nhãn `kim-dan-dung` |
| Công Nghiệp 5 Sóng | Gửi tin nhắn -> khối "Tư vấn công nghiệp" | Bật Bot + Gắn nhãn `kim-cong-nghiep` |
| Chưa rõ | Gửi tin nhắn -> khối "Chưa rõ" | Bật Bot |

Messenger cho tối đa 3 nút trên 1 tin, nên chỉ dùng đúng 3 nút này.

---

### Khối "Tư vấn dân dụng"

```
Dạ anh dùng kìm dân dụng 3 trong 1 ạ, 1 cây cắt được cả tôn 6, 9, 11 sóng 🛠️
Lưỡi làm từ 1 miếng thép SKD11 nguyên khối, cắt dây, tôi nhiệt, cắt lâu không lệch, úp khít sóng.
Anh cho em xin SĐT + địa chỉ (thôn/xóm, xã/phường, tỉnh) để em lên đơn, tặng kèm 2 đôi găng tay nhé 👇
```

### Khối "Tư vấn công nghiệp"

```
Dạ tôn 5 sóng vuông thì anh dùng kìm công nghiệp ạ, sóng 5 to nhất nên lưỡi làm riêng, cắt khớp và ngọt 🛠️
Lưỡi làm từ 1 miếng thép SKD11 nguyên khối, tôi nhiệt.
Anh cho em xin SĐT + địa chỉ (thôn/xóm, xã/phường, tỉnh) để em lên đơn, tặng kèm 2 đôi găng tay nhé 👇
```

### Khối "Chưa rõ"

```
Dạ anh làm mái nhà dân hay nhà xưởng ạ? Hoặc anh chụp giúp em mép tôn, em xem đúng loại kìm cho anh nhé 📷
```

Sau các khối này, khách gõ gì thì AI trả lời (nhờ hành động Bật Bot).

---

## LUỒNG 2: Kịch bản chăm sóc "nhắc khách chưa trả lời"

**Vào kịch bản:** khách đã nhận luồng "chào báo giá" nhưng chưa bấm nút, chưa nhắn gì.
**Dừng ngay khi:** khách trả lời, bấm nút, hoặc đã có SĐT.
**Loại tin nhắn:** Trong khoảng 24 giờ.

| Gửi sau | Nội dung | Nút |
|---|---|---|
| 30 phút | "Dạ anh ơi, anh đang làm tôn nhà dân hay nhà xưởng ạ? Em tư vấn đúng loại kìm cho anh nhé 🛠️" | Dân Dụng 3 trong 1 / Công Nghiệp 5 Sóng (cài giống Luồng 1) |
| 3 giờ | [Video cắt tôn 5-6 zem, cảnh úp khít sóng] + "Dạ em gửi anh video cắt tôn sối 6 zem, lưỡi SKD11 nguyên khối, úp lên sóng khít luôn ạ. Nhận hàng anh cắt thử, không ưng trả lại không mất phí." | Đặt hàng (Gửi tin nhắn xin SĐT + Bật Bot) |
| 20 giờ | "Dạ anh còn cần kìm không ạ? Đặt kìm em vẫn tặng 2 đôi găng tay chống cắt. Anh để lại SĐT em lên đơn cho anh nhé 👇" | (không nút) |

---

## LUỒNG 3: Kịch bản chăm sóc "đã chọn kìm, chưa để SĐT"

**Vào kịch bản:** khách có nhãn `kim-dan-dung` hoặc `kim-cong-nghiep` nhưng chưa có SĐT.
**Dừng ngay khi:** khách trả lời hoặc đã có SĐT.

| Gửi sau | Nội dung |
|---|---|
| 15 phút | "Dạ anh cho em xin SĐT và địa chỉ (thôn/xóm, xã/phường, tỉnh), em lên đơn kìm cho anh kèm 2 đôi găng tay luôn nhé 👇" |
| 3 giờ | [Video thợ dùng kìm ở công trình] + "Anh em thợ đang dùng thực tế đây anh ạ. Anh đặt về cắt thử, không ưng trả lại em, không mất đồng nào." |
| 20 giờ | "Dạ em vẫn giữ đơn kìm cho anh, anh nhắn SĐT là em gửi hàng luôn ạ 🚚" |

---

## Kiểm tra khớp với instruction AI

| Mục | Luồng | Instruction AI | Khớp? |
|---|---|---|---|
| Giá 1 cây | 1tr599k | 1tr599k | Phải giống |
| Quà | 2 đôi găng tay chống cắt | 2 đôi găng tay chống cắt | Phải giống |
| Câu hỏi chọn kìm | Dân dụng 3 trong 1 hay công nghiệp | Dân dụng 3 trong 1 hay công nghiệp | Phải giống |
| Gửi lại bảng giá | Luồng gửi 1 lần | BƯỚC 1: đã có bảng giá thì không gửi lại | OK |
| Khách bấm nút | Luồng gửi tin tư vấn + Bật Bot | BƯỚC 6: không hỏi lại loại kìm | OK |
| Giá combo | Luồng không nhắc | Chỉ báo khi khách lấy cả 2 loại | OK |
| Giảm giá | Luồng không giảm | BƯỚC 3: đếm lần ép giá | OK |

## Thử sau khi cài

1. Nick test nhắn "xin giá kìm": nhận ảnh, video, tin giá + 3 nút. Tin giá + nút nằm cuối.
2. Bấm "Dân Dụng 3 trong 1": nhận ngay tin tư vấn dân dụng.
3. Gõ "có giảm không": AI trả lời theo LẦN 1, không giảm, không hỏi lại loại kìm.
4. Gõ SĐT + địa chỉ: AI gửi mẫu xác nhận đơn có 2 đôi găng tay.
5. Nick test khác nhận luồng rồi im lặng: sau 30 phút nhận tin nhắc Luồng 2.
