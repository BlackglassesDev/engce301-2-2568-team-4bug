# 1. Introduction 

## 1.1 Purpose 

เอกสารฉบับนี้ระบุความต้องการ  (Requirements)  ของระบบ StudyBuddy - Smart Parring Study Buddy System   
มีวัตถุประสงค์เพื่อใช้เป็นแนวทางในการออกแบบ พัฒนา และทดสอบระบบ ตลอดจนเป็นข้อตกลงระหว่างทีมพัฒนากับผู้มีส่วนได้ส่วนเสีย (Stakeholders)เกี่ยวกับฟังก์ชันการทำงานและคุณภาพของระบบ  

- ใช้เป็นแนวทางในการออกแบบ (Design) และพัฒนา (Development) ระบบ 
- ใช้เป็นเกณฑ์ในการทดสอบ (Testing) และตรวจสอบความสมบูรณ์ของระบบ 
- ใช้เป็นสัญญาระหว่างทีมพัฒนากับผู้มีส่วนได้ส่วนเสีย (Stakeholders) 


## 1.2 Scope 

ระบบ StudyBuddy เป็นเว็บแอปพลิเคชันและแอปพลิเคชันมือถือ ที่มีวัตถุประสงค์เพื่อต้องการช่วยให้นักศึกษาค้นหาเพื่อนที่สนใจเรียนวิชาเดียวกัน,แลกเปลี่ยนความรู้, แชร์สรุป, และรวมกลุ่มอ่านหนังสืออย่างสะดวกและมีประสิทธิภาพ  

`ระบบ StudyBuddy จะช่วย : `
- นักศึกษา
    - หาเพื่อนเรียนและแชร์ความรู้ซึ่งกันและกัน
    - เพิ่มผลการเรียนให้กับตนเอง
    - ทำกิจกรรมเพื่อรับรางวัลต่างๆ
- บุคลากรของมหาวิทยาลัย
    - เป็นข้อมูลการทำรายงานและงานวิจัยเกี่ยวกับการทำกิจกรรม
    - ไฟล์ความรู้ เพื่อใช้ในการประกอบการสอนหรือแนะนำ
    - รายงานความคืบหน้าแก่สถาบัน


## 1.3 Definitions, Acronyms, and Abbreviations 

| Term | Definition |
|:---: | :---: |
| FR | Functional Requirement |
| NFR | Non-Functional Requirement |
| UI | User Interface |
| API | Application Programming Interface |
| UX | User Experience |
| Stakeholders | ผู้มีส่วนได้ส่วนเสีย |
| Agile | Agile Development |
| Push Notification | การแจ้งเตือนแม้ไม่ได้เข้าเว็บแอปพลิเคชั่น |
| Dashboard | ศูนย์รวมข้อมูลภาพรวม |

## 1.4 References 

- IEEE Standard 830-1998 - IEEE Recommended Practice for Software Requirements Specifications 
- User Interview Notes - สรุปจากการสัมภาษณ์ผู้ใช้งาน 15 คน (28 พ.ย. - 3 ธ.ค. 2025) 
- Stakeholder Analysis Table - ตารางวิเคราะห์ผู้มีส่วนได้ส่วนเสีย 
- Brainstorming Session Minutes - บันทึกการประชุม Brainstorm (27 พ.ย. 2025) 
- https://shorturl.asia/NQGuI - มาตรฐานการเข้ารหัสข้อมูล (DES) 

 
## 1.5 Overview 

เอกสารนี้ประกอบด้วย 3 ส่วนหลัก: 
- Section 1 (Introduction) - แนะนำภาพรวมของเอกสารและโปรเจกต์ 
- Section 2 (Overall Description) - อธิบายภาพรวมของระบบ 
- Section 3 (Specific Requirements) - ระบุความต้องการของฟังก์ชั่นหลัก 


# 2. Overall Description 

## 2.1 Product Perspective 

ระบบ StudyBuddy - Smart Parring Study Buddy System เป็นระบบแบบ integrated with other systems ที่ทำงานบน Platform  Web Browser เป็นลักษณะเว็บแอปพลิเคชั่น 

##  2.3 Assumptions and Dependencies 

- สมมติฐาน (Assumptions): 
    - ผู้ใช้มี Internet Connection ที่เสถียร 
    - ผู้ใช้มีเบราว์เซอร์ที่รองรับ HTML5 (Chrome, Firefox, Safari, Edge, Opera, Brave) 
    - มีโทรศัพท์มือถือ หรือคอมพิวเตอร์ 

- Dependencies (สิ่งที่ระบบพึ่งพา): 
    - API Email - ใช้สำหรับการยืนยันตัวตน 
    - Framework - React, MongoDB  
    - Cloud Storage - การบันทึกเก็บข้อมูลบนคลาวด์ 
    - Website - ต้องมี Web Server สำหรับ Deploy 


# 3. Specific Requirements 
## 3.1 Functional Requirements
### FR-001: User Registration 

Description: 
ผู้ใช้สามารถลงทะเบียนเข้าใช้ระบบด้วยอีเมล ชื่อผู้ใช้ รหัสผ่าน และข้อมูลส่วนตัว 

Details: 
- ให้ผู้ใช้กรอก Username Email Password และ ชื่อ-นามสกุล
- สำเร็จให้ สร้าง Account และ confirmation email

### FR-002: User Login 

Description: 
ผู้ใช้สามารถเข้าสู่ระบบด้วย Email, Username และ Password 

Details: 
- เลือกใส่ Username หรือ Email และ Passwords เพื่อ login
- มีตัวเลือกสำหรับลืมรหัสผ่าน

### FR-003: User จัดการหน้าโปรไฟล์ 

Description: 
ผู้ใช้สามารถจัดการหน้าโปรไฟล์ของตนเองได้ 

Details: 
- ผู้ใช้แก้ไขข้อมูลต่างๆ เช่น ชื่อ-นาสกุล คณะ สาขา วิชา ชั้นปี ของตนเองได้
- เปลี่ยนรูปโปรไฟล์ของตนเองที่ใช้แสดงบนเว็บ

### FR-004: แนะนำเพื่อน 

Description: 
แนะนำเพื่อนที่เรียนวิชาเดียวกันกับผู้ใช้ 

Details: 
- แนะนำเพื่อนหลังลงทะเบียนสำเร็จ
- เพื่อนที่แนะนำต้องเรียนวิชาและชั้นปี เดียวกัน 

### FR-005: การอัพโหลดไฟล์สรุป 

Description: 
หน้าการอัพโหลดไฟล์สรุปวิชาเรียน

Details: 
- ผู้ใช้เพิ่มไฟล์สรุปของผู้ใช้และแสดงบนหน้าโปรไฟล์ผู้ใช้
- แสดงเป็นหน้าโฟลเดอร์รายวิชาให้เลือกในการจัดเก็บไฟล์

### FR-006: การให้คะแนน 

Description: 
การให้คะแนนไฟล์สรุปการเรียน 

Details: 
- กดเพิ่มคะแนนให้ไฟล์สรุปของคนอื่นและตนเองได้ 1 ครั้ง
- กดอีกครั้งเพื่อ ยกเลิกการกดเพิ่มคะแนน

### FR-007: การแจ้งเตือน 

Description: 
ระบบแจ้งเตือนเมื่อเพื่อนอัพโหลดไฟล์หรือมีการเพิ่มเพื่อน 

Details: 
- แสดงการแจ้งเตือนให้กับผู้ใช้เมื่อเพื่อนมีการเพิ่มไฟล์สรุป
- แจ้งเตือนเมื่อมีการเพิ่มเพื่อนหรือการตอบรับเพื่อน
- เมื่อได้รับคะแนนจากคนอื่น

### FR-008: Leaderboard 

Description: 
ระบบ Ranking ของไฟล์ยอดนิยม 

Detail: 
- แสดงคะแนนสูงสุดแบบของแต่ละคณะและวิชาที่เรียน
- ให้รางวัลเมื่อมีการร่วมกิจกรรมต่างๆที่กำหนด

### FR-009: Dashboard 

Description: 
แสดงข้อมูลทุกอย่างที่เกิดขึ้นในระบบและสามารถดาน์โหลดได้

Details: 
- จัดทำข้อมูลขึ้นและแสดงหน้าภาพรวมของระบบทั้งหมด
- แสดงไฟล์คะแนนสูงสุดและชื่อ-นามสกุลของผู้ใช้ที่ได้คะแนนสูงสุด

# 4. Non-Functional Requirements
## NFR-001 Usability
- ผู้ใช้ทั่วไปต้องสามารถทำภารกิจหลัก เช่น ลงทะเบียนหรือ login สำเร็จภายใน 5 นาที 
- Interface ต้องรองรับภาษาไทยและภาษาอังกฤษ

## NFR-002 Reliability 
- ระบบต้องมี uptime 99% (downtime ไม่เกิน 3.65 วัน/ปี) 
- ต้องมี Backup ข้อมูลอัตโนมัติทุก 24 ชม. 

## NFR-003 Portability 
- เว็บแอปต้องทำงานได้บน Chrome, Firefox, Safari, Edge (latest versions) 
- รองรับทั้ง Desktop (1920x1080), Tablet (768x1024), และ Mobile (375x667) 

## NFR-004 Maintainability 
- ระบบต้องมีการบันทึก Log ข้อผิดพลาด (Error) ที่สำคัญทั้งหมด และสามารถเข้าถึงได้ผ่าน Centralized Logging Tool