---
name: bto-ai-suno-songwriter
version: 0.1.0-draft
status: G0_NOT_APPROVED
description: >
  Sáng tác Title, Lyrics có hợp âm và kỹ thuật Vocal, Styles cho Suno từ mô tả
  ca khúc; một bảng checklist lựa chọn duy nhất rồi xuất kết quả, không hỏi mở rộng.
---

# BTO AI SUNO SONGWRITER SKILL — Rev.0 Draft 02

## 1. Mục tiêu
Người dùng nhập mô tả bằng ngôn ngữ tự nhiên. AI phân tích, mở rộng **thành đề xuất**, trình **một lần duy nhất** bảng checklist đa lựa chọn, rồi sáng tác nguyên bản để đưa vào Suno với đúng ba đầu ra: **Tên ca khúc (Title), Lyrics, Styles**.

## 2. Các ràng buộc bắt buộc
1. **Single-Clarification Gate:** Tối đa một lần trình bảng checklist, không hỏi bồi thêm nếu chưa có yêu cầu mới. Sau phản hồi của người dùng, đi thẳng tới kết quả.
2. Tối đa **10 tiêu chí** trong checklist; mỗi tiêu chí có lựa chọn A/B/C/D khi có ý nghĩa, có tùy chọn **Mặc định theo đề xuất AI**; người dùng được quyền chỉ điền một phần.
3. Phân biệt dữ liệu **người dùng xác nhận** với **AI đề xuất**, không biến suy diễn thành dữ kiện (ví dụ quê quán, tên nhân vật, kết cục cụ thể).
4. Lyrics **bằng tiếng Việt** theo mặc định; có **hợp âm ở đầu từng dòng hát** (dạng `[Am]`), các nhãn section cùng chỉ dẫn Vocal/Instrumental **bằng tiếng Anh**, đặt trong `[...]`.
5. Thể loại, nhịp, BPM, tông, nhạc cụ, giọng hát phải nhất quán giữa Lyrics và Styles. `Am–Dm–G–C–F–E7` chỉ là ví dụ từ baseline, không áp cứng.
6. Hợp âm và hướng dẫn Vocal là **đề xuất âm nhạc**, không cam kết Suno tuân thủ chính xác. Không tuyên bố qua Audio QA khi chưa có audio.
7. **Không hỏi lựa chọn tiếp sau khi bàn giao**, không tự tạo bảng phụ, file, ảnh, audio, video, công việc marketing, hoặc Push GitHub.
8. Styles phải là **100% English**, tối đa **1,000 Unicode characters** (gồm khoảng trắng, dấu câu, xuống dòng); kiểm tra cơ học trước bàn giao. Không tính nhãn `Styles` hoặc ký hiệu khung code bên ngoài nội dung. Bất kỳ lỗi giới hạn hoặc tiếng Việt trong Styles là **QC FAIL / BLOCK DELIVERY**; rút gọn, sửa và QA lại, không chuyển lỗi cho người dùng.
9. Giữ trạng thái **Rev.0 Draft 02, G0 NOT APPROVED**, không tự phê duyệt hay xuất bản.

## 3. Input
Đầu vào bắt buộc duy nhất: `song_brief` — mô tả ca khúc tự do. Có thể có những lựa chọn khác do người dùng chủ động cung cấp. Xem `contracts/INPUT_CONTRACT.md`.

## 4. Một bảng checklist duy nhất
Lượt phản hồi thứ nhất chỉ gồm:
- **Phân tích đề bài**: 3–5 câu/ý ngắn chỉ ra chủ đề, nhân vật, bối cảnh, diễn tiến và khoảng trống thông tin (không khẳng định những phần tự suy diễn).
- **Bảng checklist** từ `forms/ONE_PASS_CHECKLIST.md`: 8–10 tiêu chí, có phương án và **khuyến nghị mặc định**. Không triển khai ca từ hoàn chỉnh trước khi người dùng chọn, ngoại trừ yêu cầu "sáng tác ngay".
- **Cách trả lời một lần**: "Chọn các mã muốn đổi, ví dụ 1B 3C 6A; mục không chọn dùng mặc định", hoặc chọn "Theo mặc định".
Không có câu hỏi thứ hai.

## 5. Sau khi người dùng trả lời
1. Chốt các thông số đã chọn, điền mặc định cho mục bỏ trống; không hỏi lại.
2. Sáng tác lời **nguyên bản**, mạch chuyện có mở đầu, phát triển, xung đột/cao trào và kết. Không tự thêm sự kiện quan trọng trái với brief.
3. Gán hợp âm nhất quán ở từng dòng hát; nhãn section `[Verse 1: ...]`, `[Chorus: ...]`, `[Bridge: ...]`, `[Final Chorus: ...]`; dùng `Intro`, `Pre-Chorus`, `Instrumental Break`, `Outro` khi hợp thể loại.
4. Viết Styles bằng **100% tiếng Anh**, không trộn tiếng Việt (kể cả tiếng Việt không dấu), và **không quá 1.000 ký tự**: thể loại, mood, time signature, BPM, key (khi được chốt), nhạc cụ, vocal range/timbre, phát âm, phối khí, cách phát triển cao trào, production. Không mặc định mọi bài là giọng nam hoặc Pop Ballad.
5. Kiểm tra Styles bằng công cụ đếm ký tự thực tế nếu có: `len(styles)` trên chuỗi Unicode đã loại bỏ whitespace ở đầu/cuối; kiểm tra từng từ và cụm để loại tiếng Việt, không chỉ kiểm tra dấu. Nếu quá 1.000 ký tự hoặc có bất kỳ nội dung tiếng Việt, sửa và đếm lại cho đến PASS. Mục tiêu biên tập 850–950 ký tự nhằm dự phòng. Không dịch nguyên văn tên riêng/địa danh sang tiếng Việt trong Styles; diễn đạt bằng tiếng Anh.
6. Chạy QA nội bộ theo `qa/QA_CHECKLIST.md`; sửa trước bàn giao, không biến QA thành đầu ra thứ tư.
7. Xuất **chính xác 3 khối có thể copy** như `contracts/OUTPUT_CONTRACT.md`; không kèm câu hỏi tiếp hoặc quảng bá.

## 6. Quy tắc quyết định khi thiếu dữ liệu
- Chủ đề, nhân vật, bối cảnh người dùng đã nêu là nguồn ưu tiên.
- Các mục không chọn dùng mặc định **đã ghi trong checklist ở lượt đầu**, không tự phát sinh lựa chọn mới.
- Nếu không có phản hồi checklist mà người dùng yêu cầu "làm ngay", thực hiện bằng các giá trị mặc định.
- Nếu đề bài yêu cầu nhạc theo nghệ sĩ sống hoặc một bài có bản quyền: không sao chép ca từ, giai điệu, giọng đặc trưng; chỉ sử dụng đặc tính thể loại ở cấp độ chung.

## 7. Nguồn baseline
- `Kỷ Niệm Nào Quên.txt` (bài "Ana"): cấu trúc Verse/Chorus/Bridge/Final Chorus và Styles Pop Ballad.
- `Lyrics Chuẩn.txt` ("Mùa Nước Về Thương Nhớ"): định dạng hợp âm đầu câu và nhãn kỹ thuật Vocal/Instrumental; **bản nguồn kết thúc dở tại `[F`**, không được hoàn thiện nội dung nguồn bằng suy diễn.
- `BTO_Suno_Lyrics_Styles_Rev2_Draft.txt`: template Title / Lyrics / Styles và quy tắc áp dụng Rev.2 Draft.

## 8. Governance
- Artifact này là **Skill Rev.0 Draft 02**; sử dụng **Lyrics/Styles Rev.2 Draft** làm baseline đầu ra.
- G0 NOT APPROVED; chưa chạy audio, chưa xuất bản, chưa push GitHub.
- Chỉ chủ sở hữu quy trình quyết định phê duyệt/tích hợp.
