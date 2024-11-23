พัฒนานอสเตอร์รีเลย์ที่ปฏิบัติตามข้อกำหนดของนอสเตอร์โปรโตคอลสำหรับการสื่อสาร
DEVELOPMENT OF THE NOSTR RELAY THAT ADHERES TO THE SPECIFICATIONS OF THE NOSTR PROTOCOL FOR DATA COMMUNICATION

วัชรพล พงษ์วิลัย

โครงงานสหกิจศึกษานี้เป็นส่วนหนึ่งของการศึกษาตามหลักสูตร
ปริญญาวิทยาศาสตรบัณฑิต สาขาวิชาเทคโนโลยีสารสนเทศ
คณะเทคโนโลยีสารสนเทศ
สถาบันเทคโนโลยีไทย-ญี่ปุ่น
พ.ศ. 2567

---

# บทที่ 1

## 1.7 ที่มาและความสำคัญของปัญหา

ในปัจจุบัน โซเชียลมีเดียได้รับความนิยมและมีบทบาทสำคัญในการสื่อสารและเชื่อมโยงผู้คนจากทั่วโลก อย่างไรก็ตาม,
การใช้งานโซเชียลมีเดียก็มีปัญหาหลายประการที่ส่งผลกระทบต่อผู้ใช้งานและผู้สร้างเนื้อหาดังนี้:

- 1.7.1 **การใช้ความสนใจของผู้ใช้เพื่อทำการขายโฆษณา**  \
  โซเชียลมีเดียใช้ข้อมูลพฤติกรรมของผู้ใช้เพื่อสร้างรายได้จากการขายโฆษณา
- 1.7.2 **การใช้เทคนิคต่าง ๆ เพื่อทำให้ผู้ใช้ติดอยู่กับแพลตฟอร์ม**  \
  มีการออกแบบเนื้อหาและฟังก์ชันที่ดึงดูดความสนใจเพื่อให้ผู้ใช้ใช้เวลานานขึ้น
  มักใช้อัลกอริธึมที่ออกแบบมาเพื่อเพิ่มเอนเกจเมน โดยกระตุ้นผู้ใช้ให้ติดตามเนื้อหาบางประเภท เช่น
  ข่าวที่สร้างความตื่นเต้นหรือเรื่องชาวบ้านโต้เถียงกันอย่างรุ่นแรง ซึ่งสามารถส่งผลเสียต่อสุขภาพจิตของผู้ใช้ เช่น
  ความเครียดหรือภาวะเสพติดโซเชียลมีเดีย
- 1.7.3 **การแสดงเนื้อหาผ่านอัลกอริธึมที่ไม่สามารถตรวจสอบได้**  \
  ระบบอัลกอริธึมจะตัดสินใจว่าเนื้อหาใดควรแสดงให้ผู้ใช้เห็น โดยที่ผู้ใช้ไม่สามารถตรวจสอบหรือปรับเปลี่ยนได้
- 1.7.4 **การควบคุมการเข้าร่วมและการเซ็นเซอร์เนื้อหา**  \
  โซเชียลมีเดียมีอำนาจตัดสินว่าใครสามารถเข้าร่วมได้หรือไม่ รวมถึงการกำหนดว่าเนื้อหาใดสมควรถูกเซ็นเซอร์
  ซึ่งส่งผลให้เสรีภาพในการแสดงความคิดเห็นของผู้ใช้งานถูกจำกัด นอกจากนี้
  ผู้สร้างเนื้อหายังต้องเผชิญกับความเสี่ยงที่จะถูกเซ็นเซอร์หรือลบบัญชี
  อันเป็นอุปสรรคต่อการแสดงออกอย่างอิสระและการสร้างสรรค์เนื้อหา
- 1.7.5 **การละเมิดความเป็นส่วนตัว**  \
  ข้อมูลส่วนตัวและพฤติกรรมของผู้ใช้ที่ถูกรวบรวมเพื่อการโฆษณาอาจถูกนำไปใช้ในทางที่ไม่เหมาะสม
  หรือเกิดการละเมิดความเป็นส่วนตัวได้
- 1.7.6 **การเสพติดและการสูญเสียเวลา**  \
  การออกแบบที่ดึงดูดความสนใจของผู้ใช้ทำให้ใช้เวลาไปกับแพลตฟอร์มมากเกินไป ซึ่งอาจส่งผลเสียต่อการดำเนินชีวิตประจำวัน
  การทำงาน และสุขภาพจิต
- 1.7.7 **การต้องปรับตัวตามการเปลี่ยนแปลงของอัลกอริธึม**  \
  ผู้สร้างเนื้อหาต้องทำความเข้าใจกับการปรับเปลี่ยนของอัลกอริธึม
  เพื่อให้เนื้อหาของพวกเขามีโอกาสถูกแสดงผลต่อผู้ใช้มากที่สุด
  ซึ่งทำให้การสร้างเนื้อหามีความท้าทายและต้องลงทุนเวลาในการศึกษาและปรับปรุงเนื้อหา

---

## 1.8 วัตถุประสงค์หรือจุดมุ่งหมายของโครงงาน

โครงงานนี้มีวัตถุประสงค์เพื่อพัฒนา Relay ซึ่งเป็นโครงสร้างพื้นฐานสำคัญของ Nostr Protocol
ที่ช่วยในการกระจายข้อมูลและการเชื่อมโยงระหว่างผู้ใช้งานและผู้สร้างเนื้อหาผ่านเครือข่ายแบบกระจายศูนย์ โดยใครๆ ก็สามารถรัน
Relay ได้ด้วยตัวเอง ติดตั้งได้ง่าย อีกทั้งยังสามารถกำหนดค่านโยบาย Relay ตามความต้องการ

---

## 1.9  ผลที่คาดว่าจะได้รับจากการปฏิบัติงานหรือพัฒนาโครงงานนี้

จากการพัฒนา Relay ซึ่งเป็นโครงสร้างพื้นฐานของ Nostr Protocol โครงงานนี้คาดว่าจะมีผลลัพธ์ที่สำคัญหลายประการ
เพื่อเสริมสร้างโซเชียลมีเดียระดับโลก ที่ทนทานต่อการปิดกั้น

- 1.9.1 **การสนับสนุนการสร้างโครงสร้างพื้นฐานที่กระจายศูนย์** \
  การพัฒนา Nostr Relay จะช่วยให้ระบบการส่งข้อมูลและการสื่อสารไม่ขึ้นกับแพลตฟอร์มหรือเซิร์ฟเวอร์ใดๆ เพียงแห่งเดียว
  ซึ่งช่วยเพิ่มความเป็นอิสระและความมั่นคงให้กับผู้ใช้งาน โดยไม่ต้องพึ่งพาผู้ให้บริการกลางหรือผู้ควบคุมแพลตฟอร์ม


- 1.9.2 **เสนอตัวเลือก Relay ที่มีประสิทธิภาพสูงในการใช้งาน** \
  Nostr Relay ที่พัฒนาขึ้นจะเป็นตัวเลือกหนึ่งที่สามารถนำไปใช้งานได้อย่างมีประสิทธิภาพสูง
  รองรับการเชื่อมต่อที่รวดเร็วและมั่นคง

---

## 1.10 นิยามศัพท์เฉพาะ

- 1.10.1 NIPs
  Nostr Implementation Possibilities
  คือชุดข้อตกลงหรือมาตรฐานที่สร้างขึ้นเพื่อกำหนดแนวทางการพัฒนาสำหรับการสื่อสารและการแลกเปลี่ยนข้อมูลระหว่าง Client กับ
  Relay

- 1.10.2 Relay

- 1.10.3 Client

- 1.10.4 Event

---

# บทที่ 2

**ทฤษฎีและเทคโนโลยีที่ใช้ในการปฏิบัติงาน**

การพัฒนา Nostr Relay มีรากฐานจากแนวคิดและเทคโนโลยีที่สำคัญ เพื่อสร้างระบบที่มีความปลอดภัย เสถียรภาพ และประสิทธิภาพสูง
โดยแต่ละองค์ประกอบที่นำมาใช้ช่วยส่งเสริมให้ Relay สามารถรองรับการสื่อสารแบบกระจายศูนย์

---

## **2.1 Cryptography**

- **2.1.1 secp256k1**  \
  ใช้งาน secp256k1 ซึ่งเป็นรูปแบบเส้นโค้งที่ใช้ในการสร้าง key pair และใช้ Schnorr signature
  ซึ่งเป็นเทคโนโลยีสำคัญที่ใช้ใน การยืนยันตัวตนตรวจสอบความถูกต้องและความน่าเชื่อถือของข้อมูล
  ช่วยป้องกันการปลอมแปลงข้อมูล และยืนยันความถูกต้องของ Event ที่รับส่งในระบบ

- **2.1.2 Schnorr Signature**  \
  เป็นเทคโนโลยีที่ใช้ในการลงนามดิจิทัล ที่มีประสิทธิภาพและปลอดภัยสูง โดยใช้ในการยืนยันความถูกต้องของข้อมูล
  และตรวจสอบตัวตนของผู้ส่งข้อมูล โดยช่วยลดขนาดข้อมูลในการเซ็นต์ และยังป้องกันการปลอมแปลงข้อมูล
  ซึ่งเป็นปัจจัยสำคัญในการสร้างความน่าเชื่อถือให้กับ Event ที่ได้รับในระบบ Nostr

---

## **2.2 WebSocket**

WebSocket เป็นโปรโตคอลที่ช่วยให้การสื่อสารระหว่าง Relay และ Client เกิดขึ้นได้อย่างรวดเร็วและต่อเนื่อง
ช่วยให้ Relay และ Client สามารถส่งและรับข้อมูลพร้อมกันได้แบบเรียลไทม์ โดยไม่ต้องสร้างการเชื่อมต่อใหม่ซ้ำ ๆ

---

## **2.3 Proof-of-Work (PoW)**

เป็นกลไกที่ช่วยเพิ่มความปลอดภัยให้กับ Relay โดยลดโอกาสในการเกิดปัญหาสแปมและการโจมตีทางไซเบอร์ เช่น DDoS
ผ่านหลักการดังนี้:

- **2.2.1 การเพิ่มต้นทุนการสร้าง Event**\  
  ก่อนที่ Client จะส่ง Event ไปยัง Relay ได้สำเร็จ จะต้องแก้โจทย์ที่เรียกว่า **cryptographic puzzle**
  โดยใช้พลังงานและเวลาในการคำนวณ Hash ที่ตรงตามเป้าของ Relay กำหนดความยากขั้นต่ำ

- **2.2.2 ป้องกันสแปม:** \
  สำหรับแก้โจทย์ ทำให้การส่ง Event ขยะหรือการหลอกลวงปริมาณมากในระยะเวลาสั้นเป็นเรื่องที่ไม่คุ้มค่า

- **2.2.3 การป้องกันการโจมตี DDoS:**  \
  ผู้โจมตีจะต้องใช้ทรัพยากรที่มหาศาลในการสร้าง Event เพื่อโจมตี Relay ช่วยลดโอกาสที่ Relay จะล่มจากการโจมตี

---

## **2.4 เทคโนโลยีที่ใช้ในการปฏิบัติงาน**

- **2.4.1 Kotlin**\
  เป็นภาษาโปรแกรมที่พัฒนาโดย JetBrains ซึ่งมีความเรียบง่าย กระชับ และปลอดภัย เหมาะสำหรับการพัฒนาซอฟต์แวร์ในยุคปัจจุบัน
  รองรับการเขียนโค้ดที่ช่วยลดข้อผิดพลาด เช่น NullPointerException มีฟีเจอร์รองรับ Coroutines ซึ่งช่วยให้จัดการงานแบบ
  Asynchronous ได้อย่างมีประสิทธิภาพ อีกทั้งทำงานร่วมกับ Java ได้อย่างไร้รอยต่อ

- **2.4.2 JVM 21**\
  การใช้ JVM มีความเสถียรภาพสูง เหมาะสำหรับการทำงานระยะยาว โดยมีการปรับจูนโค้ดตลอดการใช้งาน ทำให้แอพทำงานได้เร็ว
  มีประสิทธิภาพมากขึ้นเมื่อใช้งานต่อเนื่อง อย่างไรก็ตาม การใช้ JVM
  มีการใช้หน่วยความจำและใช้เวลาการประมวลผลมากในช่วงเริ่มต้น อีกทั้งยังรองรับ Virtual Threads (Project Loom)
  สำหรับการประมวลผลแบบ Concurrency เพิ่มความเร็วและความเสถียรของแอปพลิเคชัน

- **2.4.3 GraalVM CE 21**\
  GraalVM เป็นรันไทม์สำหรับการทำงานแบบ Polyglot ที่รองรับหลายภาษา อีกทั้งยังสามารถคอมไพล์โค้ดเป็น Native Binaries
  ทำให้รันได้ทันทีและใช้หน่วยความจำต่ำ เหมาะสำหรับระบบที่ต้องการการตอบสนองรวดเร็ว แต่ Native Binaries
  อาจมีข้อจำกัดในการทำงานบน CPU ที่แตกต่าง

- **2.4.4 Docker**\
  ใช้จัดเตรียมสภาพแวดล้อมภายในคอนเทนเนอร์ ช่วยให้การพัฒนาและการนำระบบขึ้นใช้งานเป็นไปอย่างราบรื่น
  ลดความซับซ้อนในการจัดการสภาพแวดล้อมของแอปพลิเคชัน ที่ต้องพึ่งภากัน

- **2.4.5 Micronaut Framework**\
  Micronaut เป็น Framework สำหรับการพัฒนาแอปพลิเคชันที่มีขนาดเล็กและรวดเร็ว มีฟีเจอร์ Dependency Injection (DI) และ AOT
  Compilation เพื่อเพิ่มประสิทธิภาพการทำงาน รองรับการสร้าง REST API, WebSocket และเทคโนโลยีอื่นๆ อีกมากมาย

- **2.4.6 Postgresql** \
  PostgreSQL เป็นระบบจัดการฐานข้อมูลเชิงสัมพันธ์ที่มีประสิทธิภาพและความน่าเชื่อถือสูง
  รองรับการจัดการข้อมูลปริมาณมากและการทำงานพร้อมกันหลายรายการ

- **2.4.7 GitHub และ GitHub Actions** \
  ใช้สำหรับการจัดการซอร์สโค้ด และ GitHub Actions ช่วยอำนวยความสะดวกในกระบวนการ CI/CD โดยใช้ GitHub Actions เพื่อสร้าง
  Workflow อัตโนมัติสำหรับการทดสอบแอปพลิเคชัน ช่วยเพิ่มความมั่นใจในคุณภาพของซอฟต์แวร์

- **2.4.8 Intellij IDEA Ultimate**\
  IntelliJ IDEA เป็น IDE ที่ทรงพลังและมีฟีเจอร์ครบครัน อำนวยความสะดวกสำหรับการพัฒนาภาษาทางสาย JVM อย่างเช่น Kotlin,
  Java, Scala, Groovy


