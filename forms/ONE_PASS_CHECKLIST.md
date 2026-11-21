# SINGLE-PASS CHECKLIST — ONLY ONE TABLE

AI điều chỉnh từng phương án sát `song_brief`, **không tự thay đổi các dữ kiện đã được người dùng nêu**. Mọi dòng đều có mặc định. Mỗi hàng có các lựa chọn A/B/C/D hoặc tương đương, và mô tả khuyến nghị.

| Mã | Tiêu chí | A | B | C | D | Mặc định AI |
|---|---|---|---|---|---|---|
| 01 | Thể loại | Pop Ballad | Slow Rock Ballad | Bolero | Acoustic/Folk | phù hợp brief |
| 02 | Góc kể | Nam ngôi tôi | Nữ ngôi tôi | Song ca | Người kể thứ ba | phù hợp brief |
| 03 | Cảm xúc | Hoài niệm | Day dứt | Bi thương | Chữa lành/chấp nhận | phù hợp brief |
| 04 | Kết cục | Dang dở | Đoàn tụ | Mở | Buông bỏ | phù hợp brief |
| 05 | Giọng hát | Nam baritone | Nam tenor | Nữ alto/mezzo | Song ca | phù hợp brief |
| 06 | Nhịp/tempo | 4/4 chậm 68–72 | 4/4 vừa 73–78 | 6/8 ballad | Theo thể loại khác | phù hợp brief |
| 07 | Hòa âm | Giọng thứ | Giọng trưởng | Chuyển giọng | AI quyết định | theo mood |
| 08 | Phối khí | Piano + acoustic | Guitar + sáo | Slow rock band | Mộc tối giản | phù hợp brief |
| 09 | Cao trào Vocal | Êm, tự sự | Dâng dần | Chorus mạnh | Song ca đối đáp | phù hợp brief |
| 10 | Độ dài/cấu trúc | Gọn | Tiêu chuẩn | Có solo/bridge dài | AI quyết định | tiêu chuẩn |

**Cú pháp trả lời một lần:** `01B, 02A, 04D; các mục khác mặc định.` Hoặc `Tất cả theo đề xuất AI.`

Nếu người dùng nêu sẵn tiêu chí nào, đánh dấu "đã cố định từ brief" ở tiêu chí đó; không hỏi lại. Với lựa chọn gây mâu thuẫn thông tin thực tế, ưu tiên phần mô tả cụ thể đã được xác nhận, và không tạo thêm vòng hỏi.
