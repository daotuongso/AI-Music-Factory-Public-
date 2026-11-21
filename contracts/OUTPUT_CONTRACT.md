# OUTPUT CONTRACT — EXACTLY THREE BLOCKS

## 1. TITLE
Tên ca khúc (một tên chính, không nhiều phương án, trừ khi được yêu cầu).

## 2. LYRICS
Một khối plain text, dùng được cho Suno Custom Lyrics. Quy tắc:
- Nhãn section tiếng Anh dạng `[Intro – ...]`, `[Verse 1: chest voice]`, `[Pre-Chorus: mixed voice]`, `[Chorus: controlled belting]`, `[Instrumental Break – ...]`, `[Bridge: intimate, restrained]`, `[Final Chorus: ...]`, `[Outro – ...]` **tùy tính chất tác phẩm**.
- Mỗi dòng **có lời hát** đều có ký hiệu hợp âm ở đầu dòng: `[Am] ...`.
- Hướng dẫn Vocal có ý nghĩa và thay đổi theo diễn tiến; không ép belting ở bài hát nhẹ.
- Lặp Chorus thì phải in ra trọn câu hát, không viết `[Repeat chorus]`.
- Kết thúc chính xác, không để hợp âm lẻ trống ở cuối dòng.

## 3. STYLES
Một khối văn bản **100% tiếng Anh (English only)**, sẵn để dán vào ô Styles của Suno, bao gồm genre, BPM, time signature, mood, key nếu xác định, instruments, vocals, dynamic arc, mixing.

**Hard QC Contract — MUST PASS:**
- Styles content length <= **1,000 Unicode characters**, **including** spaces, punctuation, and newlines. Count only the actual Styles text to paste (exclude labels, Markdown fences). Use `len(styles.strip())` if Python is available; report internal count in QA log only, not as an output block.
- Every natural-language phrase in Styles is in **English**. No Vietnamese words/phrases, even when written without diacritics. Foreign genre names used as established labels may appear only if English-recognized; prefer English descriptions.
- Target **850–950 characters**, but <=1,000 is the binding criterion. Keep essential music parameters and remove redundancy first.
- For any violation: **FAIL**, rewrite, recount and recheck until PASS; **never deliver** an invalid Styles block.
- Instrument / vocal instructions inside Lyrics remain per their own language convention; the Styles language gate applies independently to Styles.

Không có mục 4, không hỏi thêm trong bàn giao.
