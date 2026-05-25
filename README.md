# 🔗 Smooth-E Platform Integration

> ออกแบบระบบเชื่อม API ระหว่าง Shopee / Lazada / TikTok กับ Odoo Sale Module  
> เพื่อรองรับการทำงาน 2 ส่วนหลัก คือ Sales Order และ Platform Expense For Settlement

---

## 🎯 Overview

| หัวข้อ | รายละเอียด |
|--------|-----------|
| ระบบ | Odoo Sale Module |
| Platform | Shopee, Lazada, TikTok Shop |
| สถานะ | 🟡 In Progress  |

---

## 📦 Module 1 — Sales Order Integration

## ❗ ปัญหาที่แก้

- พนักงานต้องกรอก SO ด้วยมือทุกครั้งที่มี Order จาก Platform
- เกิด Human Error และเสียเวลา
- ระบบไม่ Real-time ทำให้ข้อมูลไม่ตรงกัน

---

## ✅ Solution

เชื่อม REST API ของแต่ละ Platform เข้ากับ Odoo  
เมื่อมี Order ใหม่ → ระบบ Auto Create SO ใน Odoo ทันที

---

## 📊 Module 2 — Platform Expense Settlement

### ❗ ปัญหา
- ฝ่าย Account ต้องดึงข้อมูลค่าใช้จ่ายจาก Platform แบบ Manual แล้วเอามา Mapping กับ Statement เอง
- ค่าใช้จ่ายจาก Shopee / Lazada / TikTok มีหลาย Item เช่น
  - ค่า Commission
  - ค่า Shipping
  - ค่า Promotion
- ทำ Settlement ช้าและเกิด Error บ่อย

### ✅ Solution
ดึง Expense Report จาก API Platform → Map เข้า Odoo Accounting  
เพื่อให้ฝ่าย Account ทำ Settlement ได้อัตโนมัติ

### 🔄 Flow
