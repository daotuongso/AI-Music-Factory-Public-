# QA CHECKLIST — RUN SILENTLY BEFORE DELIVERY

- [ ] Title chỉ 1 tên, liên quan hook/câu chuyện.
- [ ] Lyrics và Styles đồng nhất về thể loại, tempo, giọng, mood, nhạc cụ.
- [ ] Không mâu thuẫn với các dữ kiện rõ ràng của người dùng.
- [ ] Lyrics có diễn tiến kể chuyện, hình ảnh cụ thể, cao trào và kết.
- [ ] Tất cả dòng hát bắt đầu với hợp âm hợp lệ như `[Am]` hoặc `[G/B]`; không có placeholder hoặc hợp âm đứng một mình.
- [ ] Các nhãn section là chỉ dẫn tiếng Anh, không phải lời hát.
- [ ] Chỉ dẫn vocal nhất quán khả năng thể hiện và mức độ cảm xúc.
- [ ] Điệp khúc lặp được in đầy đủ; ca từ tự nhiên, dễ phát âm.
- [ ] **STYLES-LEN-001 (HARD GATE):** `len(styles.strip()) <= 1000`, counting Unicode characters including spaces/punctuation/newlines in the Styles content only. Target 850–950. If FAIL, compress and recount; block delivery until PASS.
- [ ] **STYLES-LANG-002 (HARD GATE):** 100% English natural-language content, no Vietnamese text (with or without diacritics). Review semantically; diacritic-only validation is insufficient. If FAIL, rewrite and recheck; block delivery until PASS.
- [ ] **STYLES-CONTENT-003:** Genre, time signature/BPM, emotional mood, instruments, vocal timbre/techniques, dynamics and production are coherent with Lyrics, without excess repetition.
- [ ] **STYLES-BOUNDARY-004:** Count excludes the `Styles` heading and Markdown code fences; excludes no other characters from the pasted text.
- [ ] Styles QA failure invokes rewrite -> recount -> language check -> content check; never present an invalid draft as final.
- [ ] Đầu ra đúng ba khối Title / Lyrics / Styles; không thêm câu hỏi hậu bàn giao.
- [ ] Không tuyên bố bản audio đạt yêu cầu khi chưa được kiểm tra.
- [ ] Draft / G0 NOT APPROVED; không tự phát hành hoặc Push.
