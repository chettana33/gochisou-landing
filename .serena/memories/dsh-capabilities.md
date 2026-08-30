## กติกา serena กันพลาด (31 ส.ค. 69 — lesson: replace fail เพราะ index ยังโหลด)

1. หลัง `activate_project` ห้ามใช้ `replace_content`/`replace_in_files` ทันที — ต้องเช็ค LSP ready ก่อน: `get_current_config` → ดู `Language server status: ready`
2. ยังไม่ ready = รอ/ใช้ pwsh แทน (`[System.IO.File]::ReadAllText/WriteAllText` — ตัวสำรองตาม lessons-learned #7)
3. replace fail ครั้งเดียว ("No matches") = อย่าลองซ้ำ — สลับ pwsh ทันที (path ไทย + serena index อาจ mismatch)
4. ไฟล์ H: (Google Drive) งานเขียน — ใช้ serena ก่อน; fail = pwsh; ห้ามใช้ edit tool ตรง (พัง SetFileSecurityW, lessons #1)
5. ไฟล์ D:\GitHub (โค้ด/งานใหญ่) — ใช้ serena (รู้ symbol/โครงสร้าง/memory); งาน file ops ง่าย = DSH edit/glob/grep ตรง (AGENTS §21)
6. อ่านผลหลังเขียนทุกครั้ง (read ตรวจ) — ไม่ Trust แต่ Verify
7. ส่งค่า `max_answer_chars` จำกัดผล serena ทุกครั้ง; อ่านเป็น chunk (offset/limit)

## โปรเจกต์ serena
- Obsidian-Vault = H:\My Drive\พาเที่ยว\Obsidian-Vault (activate ก่อนงาน Vault)
- gochisou-landing = D:\GitHub\gochisou-landing (สร้าง 31 ส.ค. 69 — ถ้าไม่เจอใน list ให้ activate ด้วย path เต็ม)
- อื่นๆ = D:\GitHub\<repo> ตาม MASTER_INDEX_PROJECTS