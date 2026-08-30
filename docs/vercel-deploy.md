# Gochisou Landing — Deploy Vercel + Domain

## สถานะ (31 ส.ค. 69)

| รายการ | สถานะ |
|---|---|
| Vercel project | `gochisou-landing` (team senei-kotsu-invoice — ทีมรวมของพี่เจ) |
| Deploy URL | https://gochisou-landing.vercel.app ✅ (ทำงาน 200) |
| Domain ใน Vercel | `gochisou.ichinotour-thailand.com` — เพิ่มแล้ว, รอ DNS |
| GH Pages (backup) | https://chettana33.github.io/gochisou-landing/ ✅ |

## พี่เจ้าต้องทำ: เพิ่ม CNAME ที่ Squarespace (ครั้งเดียว)

domain `ichinotour-thailand.com` ใช้ DNS ของ Squarespace (`nsa1-4.squarespacedns.com`)

1. เปิด Squarespace → Domains → `ichinotour-thailand.com` → DNS Settings
2. เพิ่ม CNAME record:
   - **Host / Name:** `gochisou`
   - **Points to / Value:** `cname.vercel-dns.com`
   - TTL: เริ่มต้น (3600)
3. Save → รอ propagate (ไม่เกิน 1-24 ชม.)

## ตรวจหลัง DNS ตั้ง

```powershell
Resolve-DnsName gochisou.ichinotour-thailand.com -Type CNAME
# ควรได้: cname.vercel-dns.com

vercel domains verify gochisou.ichinotour-thailand.com --scope senei-kotsu-invoice
```

แล้วเปิด https://gochisou.ichinotour-thailand.com — ควรเจอ landing.

## Redeploy หลังแก้ไฟล์

```powershell
cd D:\GitHub\gochisou-landing
vercel --prod --yes --scope senei-kotsu-invoice
```

## หมายเหตุ

- ใช้ Vercel (ไม่ใช่ GH Pages) เป็นหลักสำหรับโดเมนนี้; GH Pages เก็บเป็น backup
- git push ยังทำอยู่ (source of truth = GitHub)
