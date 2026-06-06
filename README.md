# 🔗 Smooth-E Platform Integration

> ออกแบบระบบเชื่อม API ระหว่าง Shopee / Lazada / TikTok กับ Odoo Sale Module  
> เพื่อดึงข้อมูลจาก Sale Orderและ ค่าใช้จ่าย ในแต่ละ Platform มาอยู่ในหน้าระบบ ERP

---

## 🎯 Overview

| หัวข้อ | รายละเอียด |
|--------|-----------|
| ระบบ | Odoo Sale Module |
| Platform | Shopee, Lazada, TikTok Shop |
| สถานะ | 🟡 In Progress  |

## Software Specification
- [Design Specification Platform Expense](https://basicsolutionco-my.sharepoint.com/:x:/r/personal/trin_r_odoo365_co/_layouts/15/Doc.aspx?sourcedoc=%7B2DE71CF7-3CB8-42EA-9759-12F1F60E40FD%7D&file=Software%20Specification-Smooth%20E-%20Marketplace%20expense.xlsx&action=default&mobileredirect=true)


---

## 📦 Module 1 — Sales Order Integration

## ❗ ปัญหาที่แก้

- เมื่อก่อนใช้ Oracle พนักงานต้องกรอก SO ด้วยมือทุกครั้งที่มี Order จาก Platform
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
