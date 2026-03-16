# Project Proposal

## Project Name
**Gold Knowledge Chatbot System**

---

# 1. Problem Statement

## WHO (ใครเดือดร้อน)
นักลงทุนมือใหม่ และผู้ที่สนใจลงทุนทองคำ

## WHAT (ปัญหาคืออะไร)
ผู้ใช้งานขาดความรู้พื้นฐานเกี่ยวกับทองคำ เช่น

- ราคาทองคำ
- การลงทุนทองคำ
- วิธีวิเคราะห์แนวโน้มราคา

ข้อมูลเกี่ยวกับทองคำกระจายอยู่หลายเว็บไซต์ ทำให้ค้นหายากและเสียเวลา

## WHEN (เกิดบ่อยแค่ไหน)
ปัญหานี้เกิดขึ้นบ่อยเมื่อ

- ผู้ใช้งานต้องการศึกษาการลงทุนทองคำ
- ราคาทองมีการเปลี่ยนแปลง
- ต้องการข้อมูลก่อนตัดสินใจซื้อหรือขายทอง

## HOW MUCH (เสียเวลา/เงินเท่าไหร่)
ผู้ใช้ต้องเสียเวลาในการค้นหาข้อมูลจากหลายแหล่ง  
และอาจตัดสินใจลงทุนผิดพลาด ส่งผลให้สูญเสียเงิน

---

# 2. Proposed Solution

สร้าง **Gold Knowledge Chatbot**

ที่สามารถ

- ตอบคำถามเกี่ยวกับทองคำ
- ให้ความรู้เกี่ยวกับการลงทุนทองคำ
- แสดงราคาทองล่าสุดจาก API

เพื่อช่วยให้ผู้ใช้งานสามารถเข้าถึงข้อมูลเกี่ยวกับทองคำได้ง่ายและรวดเร็วผ่านระบบแชทบอท

---

# 3. System Overview

ระบบจะใช้ Chatbot ที่เชื่อมต่อกับ AI และฐานความรู้เกี่ยวกับทองคำ

ผู้ใช้สามารถถามคำถาม เช่น

- ราคาทองวันนี้เท่าไหร่
- ทองแท่งกับทองรูปพรรณต่างกันยังไง
- ลงทุนทองดีไหม

ระบบจะตอบโดยใช้

- AI Agent
- Knowledge Base
- Gold Price API

---

# 4. System Architecture

```mermaid
flowchart LR

User[User]

User --> Chat[Discord Chat]

Chat --> Webhook[Webhook]

Webhook --> n8n[n8n Workflow]

n8n --> IFNode{IF Node}

IFNode --> AIAgent[AI Agent]

AIAgent --> Retriever[Retriever]

Retriever --> KnowledgeBase[(Gold Knowledge Base)]

AIAgent --> GoldAPI[Gold Price API]

GoldAPI --> GoldData[(Gold Price Data)]

AIAgent --> CodeNode[Code Node]

CodeNode --> Discord[Send Message to Discord]

Discord --> User
