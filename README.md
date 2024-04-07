## futureskill
Class-Project

#วาดภาพ Process Step ต่าง ๆ ของ Devops Pipeline รวมถึงใส่ Tools ในแต่ละ Step 
#วาดภาพ Infrastructure Architecture โดยมีโจทย์ตามนั้น

มีเครื่องคอมพิวเตอร์ 3 เครื่องอยู่ Network zone Internet Facing 
    * เครื่องที่ 1 ชื่อ Squid proxy เครื่องนี้รับ traffic จาก Zone private zone ออก Internet 
    * เครื่องที่ 2 ชื่อ Ha proxy เครื่องนี้รับ traffic จาก internet ไปยัง private zone 
    * เครื่องที่ 3 ชื่อ Control ให้ Devops Engineer เข้ามาควบคุมเครื่องภายใน private zone
 
มี Kubernetes Cluster 3 Master 3 Worker อยู่ใน Private Zone 
    * เครื่อง Control จะต้องต่อเข้า Master Node 
    * เครื่อง Worker Node ต้องต่อออก Squid Proxy 
    * เครื่อง Haproxy ต้องต่อออก WorkerNode
เครื่อง SQL Server (Database) อยู่ใน Internal zone
    * Kubernetes Worker Node ต้องต่อเข้า SQL Server
