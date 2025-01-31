
# Leveraging WangchanBERTa for NLP-Driven Insights into Bangkok's Road Complaints via Traffy Fondue

<p align="center">
  <img width = 200 heigth =200 src="https://storage.googleapis.com/traffy_public_bucket/traffy_logo/Image_fondue_logo.png">
</p>

กรุงเทพมีปัญหาเรื่องโครงสร้างพื้นฐานที่ซับซ้อน แม้จะมีช่องทางให้ประชาชนร้องเรียน เช่น แอปพลิเคชัน Traffy Fondue แต่ข้อมูลที่ได้รับมักมีปริมาณมากและซับซ้อน ทำให้ยากต่อการวิเคราะห์และจัดการอย่างมีประสิทธิภาพ และในแอพพลิเคชั่น Traffy Fondue ประเภทของเรื่องแจ้งที่ติด Top 5 ตลอด คือ ถนน เช่น การชำรุดเสียหาย การจราจรติดขัด และการจัดการที่ล่าช้า




## เป้าหมายของโปรเจคนี้:
โปรเจคนี้มุ่งเน้น:

1. ใช้ WangchanBERTa ในการสรุปและจัดลำดับความสำคัญของข้อมูลร้องเรียนจาก Traffy Fondue
2. วิเคราะห์ข้อมูลเชิงลึกเกี่ยวกับปัญหาถนนในกรุงเทพมหานคร
3. เสนอวิธีการที่สามารถช่วยหน่วยงานที่เกี่ยวข้องตัดสินใจแก้ไขปัญหาอย่างมีประสิทธิภาพ

<p align="center">
  <img src="https://github.com/NoppalitP/RoadVoice-BKK/blob/main/Screenshot%202025-01-12%20202920.png">
</p>

## วิธีการ:
  ### 1. การเก็บข้อมูลและการเตรียมข้อมูล:
  ข้อมุลเก็บรวบรวมมาจากแอพลิเคชั่น Traffy Fondue สามารถเอาได้จาก traffy.in.th มีการใช้ตัวตัดคำ sub-word สำหรับ WangchanBERTa และคำนวณ Sentence Vector จากนั้นนำไปคำนวณหา Similarity Matrix
  <p align="center">
  <img src="https://github.com/user-attachments/assets/1a2531ee-722a-486e-a412-6eb5ae9d7f3d">
</p>



  ### 2. สร้างกราฟจาก Similarity Matrix และคำนวณ PageRank:
  ใช้ Library NetworkX แปลงค่า Sentence Similarity ใน Matrix แถวที่ i และคอลัมน์ที่ j ไปเป็น Weight ที่อยู่บนเส้นเชื่อม (Edge) ของประโยค i และประโยค j ก่อนที่จะนำไปคำนวณค่า PageRank
    <p align="center">
  <img src="https://github.com/user-attachments/assets/0939517a-ca5a-43f8-ae0a-22770f6952b3">
</p>

  ### 3.ผลลัพธ์:
  ```
<p align="center">
  <img src="https://github.com/user-attachments/assets/dfd5e392-5bb2-44f8-b094-a2237224fd26">
</p>
  ```

## ข้อสรุปที่ได้จากการศึกษา
การวิเคราะห์ข้อมูลร้องเรียนเกี่ยวกับปัญหาถนนในกรุงเทพฯ จากแอปพลิเคชัน Traffy Fondue ทำให้ได้ข้อสรุปสำคัญดังนี้:
* ผิวถนนชำรุด เช่น หลุมบ่อ ฝาท่อไม่เรียบ หรือมีการขุดถนนแต่ไม่ซ่อมแซมอย่างครบถ้วน
* การจอดรถกีดขวาง ส่งผลต่อการจราจรและอาจนำไปสู่อุบัติเหตุ
* ความล่าช้าในการแก้ไขปัญหาหลังการร้องเรียน ส่งผลให้ปัญหายืดเยื้อและสร้างความไม่พอใจให้กับประชาชน



