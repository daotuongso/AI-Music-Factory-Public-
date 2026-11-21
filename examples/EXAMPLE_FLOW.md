# EXAMPLE FLOW (SYNTHETIC)

## User input
"Sáng tác tình yêu tan vỡ của đôi trai gái miền Tây. Chàng đi học ở thành thị, nàng ở quê đợi, cuối cùng không đến được với nhau."

## AI response 1
Phân tích: Bối cảnh miền Tây sông nước; chàng rời quê đi học; nàng chờ; kết cục **dang dở (đã cố định)**. Các chi tiết như nguyên nhân chia tay, giọng kể và thể loại là đề xuất, chưa phải sự kiện xác nhận.

AI trình **một** bảng checklist ở `forms/ONE_PASS_CHECKLIST.md`, đánh dấu `04A` đã cố định bởi brief, gợi ý `01B` Slow Rock Ballad và `02A` nam ngôi tôi. Người dùng chọn `01A, 02A; các mục còn lại mặc định`.

## AI response 2
Chỉ xuất ba khối:

### TITLE
Bến Chiều Không Đợi

### LYRICS
```text
[Intro – Gentle piano, acoustic guitar, distant bamboo flute]

[Verse 1: warm chest voice, intimate storytelling]
[Am] Anh theo con nước rời quê lên phố
[Dm] Em đứng bên đò, giữ hộ lời thương
[G] Mùa thi nối tiếp mùa mưa lặng lẽ
[C] Đèn thành đô sáng, bến nhỏ còn sương.

[Chorus: controlled emotional lift, sustained notes]
[Dm] Bến chiều ơi, còn ai chờ ai nữa
[Am] Con nước đầy, mà lời hẹn vơi đi
[E7] Anh về muộn, qua bao mùa thương nhớ
[Am] Gọi tên người, chỉ nghe sóng thầm thì.

[Outro – Gentle acoustic guitar, natural ending]
```

### STYLES
```text
Vietnamese contemporary Pop Ballad, slow 4/4 around 74 BPM, A minor, nostalgic and bittersweet. Gentle piano, fingerpicked acoustic guitar, warm bass, soft drums, distant bamboo flute. Warm male baritone, clear Vietnamese diction, intimate chest voice in verses, expressive controlled lift in chorus. Spacious organic vocal-forward mix and restrained ending.
```

**Lưu ý:** ví dụ ngắn để minh họa định dạng, **không** phải bài hoàn chỉnh chuẩn phát hành.

## Styles QC example
- A draft Styles block with 1,004 characters: **FAIL** even if entirely in English. Remove redundant descriptors; recount.
- A 920-character Styles block containing Vietnamese words: **FAIL**; rewrite these phrases into English and recheck.
- A 920-character English-only Styles block consistent with Lyrics: **PASS** for both hard gates.
