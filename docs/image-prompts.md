# Gochisou Landing — ชุด Prompt เจ้นภาพ (Nano Banana / Gemini)

> วิธีใช้: พี่เจเปิด labs.google / gemini.google.com ด้วย `chettana33@gmail.com` → ก๊อป prompt ข้างล่าง → gen → บันทึกลง `assets/` ตามชื่อไฟล์ที่ระบุ → ผมตรวจด้วย modlens + ปรับ CSS.
> ห้ามใส่ข้อมูลลับ/ราคาจริง (AGENTS §16) — ใช้ภาพอาหาร/บรรยากาศตัวอย่างเท่านั้น.

## ข้อกำหนดภาพรวม

- สไตล์: ภาพถ่ายอาหารญี่ปุ่นระดับ premium — แสงอบอุ่น (warm golden), ใกล้เคียงจริง (photorealistic), depth of field, เนื้อสัมผัสชัด
- โทนสี: ตรงกับธีม landing (พื้น #f9f9f9, สีหลักแดง #910022, ทอง #C5A059) — ภาพควรมีแดง/ทอง/ไม้/ถ่าน เป็น accent
- ขนาด: hero ใช้ 1920x1080 (16:9), gallery ใช้ 1:1 (square)
- ไม่มีข้อความ/โลโก้ในภาพ (text ฝังใน HTML)

---

## 1. hero.jpg (1920x1080) — ภาพหลักหน้าแรก

**เป้าหมาย:** แทนภาพเดิม (omakase counter) ด้วยภาพที่สะดุดตา = อาหารญี่ปุ่น premium + บรรยากาศโตเกียวกลางคืน

Prompt:
```
Photorealistic hero banner of premium Japanese cuisine, 16:9. Left side: close-up of
chef's hand plating a beautiful toro nigiri with gold leaf on black ceramic plate,
steam rising. Right side: blurred background of an upscale Tokyo restaurant at night,
warm lantern light, dark wood counter, shallow depth of field. Color palette: deep red,
gold, warm amber, charcoal black. Moody but appetizing, Michelin-star atmosphere.
No text, no watermark, no logo.
```

ตัวเลือก B (ถ้าอยากได้ย่าน/ไฟกลางคืน):
```
Photorealistic night scene of a narrow Tokyo alley (yokocho) with small izakaya
restaurants, red paper lanterns, warm glowing signs (abstract, no readable text),
steam from food stalls, one chef grilling yakitori in foreground. Premium travel
photography style, cinematic warm tones, 16:9. No text, no watermark.
```

---

## 2. food-grid.jpg (ใช้ crop 3x2 = 6 ภาพจากไฟล์เดียว)

**เป้าหมาย:** ปัจจุบัน HTML crop ภาพเดียวเป็น 6 ช่อง (`background-size: 300% 200%`) — gen ภาพ collage 6 ช่องให้ crop กลายเป็น 6 จานต่างกัน

Prompt:
```
Photorealistic collage grid 3x2 of six different premium Japanese dishes, each cell
separated by thin dark lines, all on dark ceramic or wooden backgrounds:
1) Sushi platter with toro, uni, ikura on black slate
2) Wagyu sukiyaki with raw egg in iron pot
3) Sashimi moriawase with wasabi and shiso
4) Grilled unagi over rice in lacquer box
5) Ramen with chashu, ajitama egg, nori
6) Tempura platter with matcha salt
Warm restaurant lighting, consistent color grading (red/gold/charcoal), appetizing,
Michelin quality. No text, no watermark, no logo. Square aspect ratio.
```

---

## 3. รูปสำรอง/โซเชียล (ไม่บังคับรอบแรก)

- **logo_round.png** (512x512): โลโก้ 御 Gochisou วงกลมพื้นแดง #910022 ตัวอักษรขาว — สำหรับ favicon/profile
  ```
  Minimalist round app icon, deep red (#910022) background, white Japanese kanji 御
  centered, subtle gold ring border, flat vector style, no other text.
  ```
- **og-image.png** (1200x630): ภาพโซเชียลแชร์ (เมื่อทำ TikTok/แชร์ LINE)
  ```
  Premium social banner 1200x630: dark charcoal background, hero sushi photo right
  side, left side big Thai text "จองร้านดังที่จองยาก" in white bold sans-serif,
  small gold text "Gochisou by Ichinotour" below, red accent line. Thai text must be
  perfectly readable.
  ```

---

## QA หลัง gen

1. บันทึกไฟล์ → ผมตรวจด้วย modlens (text เพี้ยน/ไม่ใช่ไทย/โลโก้ปลอม)
2. วางใน `assets/` ทับชื่อเดิม หรือชื่อใหม่แล้วแก้ HTML
3. commit + push → GH Pages deploy อัตโนมัติ
