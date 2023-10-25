# ศึกษา Docker, Home assistant, Node-RED และ MQTT

### Node-RED
Node-RED เป็นเครื่องมือสำหรับนักพัฒนาโปรแกรมในการเชื่อมต่ออุปกรณ์ฮาร์ดแวร์เข้ากับ APIs (Application Programming Interface) ซึ่งเป็นการพัฒนาโปรแกรมแบบ Flow-Based Programming ที่มีหน้า UI สำหรับนักพัฒนาให้ใช้งานผ่าน Web Browser ทำให้การเชื่อมต่อเส้นทางการไหลของข้อมูลนั้นเป็นเรื่องง่าย 
เนื่องจาก Node-RED เป็น Flow-Based Programming แค่เพียงเลือก Node มาวางแล้วเชื่อมต่อก็สามารถควบคุม I/O ได้ โดย Node-RED จะมี Node ให้เลือกใช้งานอย่างหลากหลาย และ Node-Red เหมาะสำหรับการทำงานกับ IoT (Internet of Things) เพราะสามารถรับส่งข้อมูลจากอุปกรณ์หรือบริการที่ใช้โปรโตคอลหรือรูปแบบข้อมูลต่างๆได้    
__ข้อดี__
* Easy to use: ไม่ต้องเขียนโค้ดมาก เนื่องทำงานแบบ flow-based programming
* Many node option: มี node ที่พร้อมใช้งานมากมาย และสามารถติดตั้งเพิ่มเติมผ่าน npm ได้
* Can create node: สามารถสร้าง node เองได้ตามความต้องการ
* Open source: เป็น open source software จึงไม่มีค่าใช้จ่าย
* Deploy: สามารถ deploy ได้ทั้งบน device เช่น Raspberry Pi หรือบน cloud platform
  
 __ข้อเสีย__  
 
* Created node not work: node ที่สร้างเองอาจไม่สามารถทำงานได้ดีกับ node อื่นๆ
* Stylishness: node-red dashboard ที่ใช้สร้างหน้าจอ UI อาจไม่สวยหรือตกแต่งได้น้อย
* Performance: performance ของ Node-RED อาจไม่ดีเทียบกับการเขียนโค้ดเอง
