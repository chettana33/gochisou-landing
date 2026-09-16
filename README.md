# Gochisou — รับจองร้านอาหารทั่วประเทศญี่ปุ่น (by Ichinotour)

Landing page จองร้านอาหารญี่ปุ่น B2B+B2C — ฟอร์มขอจอง → Firestore (`quotations`, source=`gochisou`)

- URL จริง: https://gochisou.ichinotour-thailand.com (Vercel) · สำรอง: https://chettana33.github.io/gochisou-landing/ (GitHub Pages, branch `main`)
- Design base: Stitch mockup (Gochisou Brand Identity — Minimalist ญี่ปุ่น, DESIGN.md ใน Vault `พาเที่ยว/Gochisou/`)
- ฟอร์ม → Firestore project `peppy-vertex-468800-g2` database `ai-studio-20401de6-...` collection `quotations` (rules allow create)
- LINE แจ้ง: poll script (`tools/gochisou_line.py` — ยังไม่ทำ)
- อัตรา: กรุ๊ป ≤40 = 3,000 JPY · 40+ = 5,000 JPY (ต่อร้าน/ต่อการจอง) · คิดเฉพาะจองสำเร็จ · 09:00-18:00 น. (JST)
- ติดต่อ (ลูกค้า): LINE `@gochisou` (https://page.line.me/gochisou) · อีเมล gochisou@ichinotour-thailand.com — **ไม่แสดงเบอร์โทรบนหน้าเว็บ** (มติ 16 ก.ย. 69: ให้ลูกค้าติดต่อทาง LINE/อีเมลเท่านั้น)
- หมายเหตุ deploy: โดเมนจริงเสิร์ฟโดย **Vercel** (โปรเจกต์อยู่ใต้ team) → push อย่างเดียวโดเมนจริงไม่อัปเดต ต้อง `vercel deploy --prod` ด้วยสิทธิ์ของทีม

## Dev

```bash
python -m http.server 8080   # ทดสอบ local
```

Push main → Pages auto deploy.
