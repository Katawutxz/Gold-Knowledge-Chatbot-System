# Gold Knowledge Chatbot System

AI Chatbot สำหรับให้ความรู้เกี่ยวกับทองคำ เช่น  
- ราคาทองล่าสุด
- การลงทุนทอง
- ความรู้พื้นฐานเกี่ยวกับทองคำ

ระบบนี้ช่วยให้นักลงทุนมือใหม่สามารถเข้าถึงข้อมูลได้ง่ายและรวดเร็วผ่าน Chatbot

---

# Problem Statement

### WHO
นักลงทุนมือใหม่ และผู้ที่สนใจลงทุนทองคำ

### WHAT
ผู้ใช้งานขาดความรู้พื้นฐานเกี่ยวกับทองคำ เช่น
- ราคาทอง
- วิธีลงทุนทอง
- การวิเคราะห์แนวโน้มราคา

ข้อมูลกระจายอยู่หลายแหล่ง ทำให้ค้นหายาก

### WHEN
เกิดขึ้นบ่อยเมื่อ
- ผู้ใช้งานต้องการศึกษาการลงทุนทอง
- ราคาทองมีการเปลี่ยนแปลง

### HOW MUCH
ผู้ใช้เสียเวลาในการค้นหาข้อมูลจากหลายเว็บไซต์  
และอาจตัดสินใจลงทุนผิดพลาด

---

# Proposed Solution

สร้าง **Gold Knowledge Chatbot**

ที่สามารถ

- ตอบคำถามเกี่ยวกับทองคำ
- ให้ความรู้เรื่องการลงทุน
- ดึงราคาทองล่าสุดจาก API

เพื่อช่วยให้ผู้ใช้เข้าถึงข้อมูลได้รวดเร็ว

---

# System Architecture

```mermaid
flowchart LR

User[User]

User --> Webhook[Webhook Trigger]

Webhook --> n8n[n8n Workflow]

n8n --> IFNode{IF Node<br>Check Question}

IFNode --> AIAgent[AI Agent]

AIAgent --> Retriever[Retriever]

Retriever --> KnowledgeBase[(Gold Knowledge Base)]

AIAgent --> GoldAPI[Gold Price API]

GoldAPI --> GoldPrice[(Gold Price Data)]

AIAgent --> CodeNode[Code Node<br>Format Answer]

CodeNode --> Discord[Send to Discord]

Discord --> User

