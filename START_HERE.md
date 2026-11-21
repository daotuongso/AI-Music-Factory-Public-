# START HERE — BTO AI Suno Songwriter Skill

**Version:** Rev.0 Draft 02  
**Status:** DRAFT — G0 NOT APPROVED  
**Purpose:** Biến mô tả ca khúc của người dùng thành Title, Lyrics có hợp âm và chỉ dẫn Vocal, Styles dùng cho Suno.

## Luồng tối đa 2 lượt phản hồi từ AI

1. **Lượt AI 1 — phân tích & checklist:** Tóm tắt chủ đề người dùng đưa ra, đề xuất lựa chọn trong **một bảng checklist duy nhất** (không quá 10 dòng), kèm giá trị khuyến nghị/mặc định. Không sáng tác hoàn chỉnh lúc này trừ khi người dùng yêu cầu đi thẳng vào sáng tác.
2. **Lượt AI 2 — bàn giao:** Sau đúng **một lượt** người dùng chọn phương án (hoặc yêu cầu dùng mặc định), lập **Title, Lyrics, Styles** hoàn chỉnh; tự QA nội bộ. **Không đặt câu hỏi tiếp, không tự mở thêm các bước, không lặp checklist.**

Nếu người dùng bỏ trống một số lựa chọn, áp dụng mặc định đã công bố. Nếu người dùng thay đổi đề bài thì chỉ thay đổi các ràng buộc liên quan. Không xuất bản, tạo audio, push, phê duyệt hoặc thay đổi tài liệu nguồn nếu chưa được giao.

Xem [`SKILL.md`](SKILL.md) và các thư mục `contracts/`, `workflow/`, `forms/`, `examples/`, `qa/`.

## Styles hard QC (new)
- Styles: 100% English only; maximum 1,000 characters including spaces and punctuation.
- QA gate fails and delivery stops until text is revised and rechecked. Aim for 850–950 characters.
