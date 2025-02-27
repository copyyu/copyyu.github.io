# 🔒 3.2.2 ตรวจสอบว่า Session Tokens มี Entropy อย่างน้อย 64 บิต  

## 📜 **Description**  
- This requirement ensures that session tokens are sufficiently random and resistant to prediction or brute-force attacks. A session token should have at least 64 bits of entropy, meaning it should be generated using a cryptographically secure random number generator (CSPRNG) and be unpredictable.

## 🤖 **ChatGPT **  
ข้อกำหนดนี้หมายความว่า **โทเค็นของเซสชัน (Session Tokens)** ต้องมีความซับซ้อนอย่างน้อย **64 บิตของเอนโทรปี (Entropy)** เพื่อให้มั่นใจว่าโทเค็นมีความสุ่มเพียงพอ และไม่สามารถคาดเดาหรือเดาซ้ำได้ง่าย ซึ่งช่วยป้องกันการโจมตีแบบ **Session Prediction** หรือ **Session Fixation**  

### 🔎 **คำอธิบายเพิ่มเติม**  
- **Entropy (เอนโทรปี)** หมายถึงระดับความไม่แน่นอนหรือความยากในการคาดเดาค่าโทเค็น  
- **64 บิตของเอนโทรปี** หมายความว่าโทเค็นมีจำนวนค่าที่เป็นไปได้อย่างน้อย **\(2^{64}\)** ค่าที่แตกต่างกัน  
- หากโทเค็นมีเอนโทรปีต่ำเกินไป แฮกเกอร์อาจใช้ **Brute Force** เดาโทเค็นของผู้ใช้และเข้ายึดเซสชันได้  

### ✅ **แนวทางปฏิบัติที่ดี**  
- ใช้ **Cryptographically Secure Random Number Generators (CSPRNG)** เช่น:  
  - **Node.js:** `crypto.randomBytes(32).toString('hex')`  
  - **Python:** `secrets.token_hex(32)`  
- หลีกเลี่ยงการใช้ค่าที่คาดเดาได้ เช่น **Sequential Numbers, Usernames, Timestamps**  
- ตรวจสอบให้แน่ใจว่าโทเค็นมีความยาวและความสุ่มเพียงพอ  

## 🌍 **Gemini **  
ข้อกำหนดนี้เป็นส่วนหนึ่งของมาตรฐานหรือแนวปฏิบัติด้านความปลอดภัย ซึ่งมุ่งเน้นไปที่การ **จัดการเซสชันของผู้ใช้** ในแอปพลิเคชันเว็บ  

### 📌 **คำศัพท์ที่เกี่ยวข้อง**  
- **Session Token:** ข้อมูลที่ใช้ระบุตัวตนของผู้ใช้ขณะใช้งานเว็บไซต์  
- **Entropy:** ค่าที่บ่งบอกถึงความสุ่มของข้อมูล ยิ่งสูง ยิ่งคาดเดายาก  
- **64 บิต:** หน่วยวัดเอนโทรปี โดยมีค่าที่เป็นไปได้ **\(2^{64}\)** ค่า  

### ⚠ **ความสำคัญของข้อกำหนดนี้**  
หากผู้โจมตีสามารถขโมยหรือปลอมแปลงโทเค็นเซสชันได้ **บัญชีของผู้ใช้และข้อมูลส่วนตัวจะถูกเข้าถึงได้** ดังนั้น การสร้างโทเค็นที่ปลอดภัยจึงเป็นสิ่งสำคัญมาก  

## ✍ **Myself**  
ในการตรวจสอบว่า session token มี entropy อย่างน้อย 64 บิต เราสามารถใช้หลักการคำนวณ entropy ของข้อมูล โดยทั่วไป entropy ของ token คำนวณจากจำนวนบิตของข้อมูลที่คาดเดาไม่ได้ ยิ่ง entropy สูง ความปลอดภัยของ token ยิ่งดี  

## 🧑‍💻 **My Team**  
- **👤 6530250352 Chayapol Jitnaphets**  
- **👤 6530250263 Siraphop Chootong** 🌐 [Security Requirement](https://nmpsz.github.io/security-requirement)  


