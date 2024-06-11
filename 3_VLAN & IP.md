# VLAN & IP

**Vlan(Virtual area network)** หมายถึงกลุ่ม device ที่เชื่อมต่อกันและมีการแชร์ Broadcast domain ร่วมกัน

1. การสร้าง VLAN ยกตัวอย่างเช่น ต้องการสร้าง VLAN 1000
~~~
system-view
vlan 1000
quit
~~~
2. การกำหนด IP Address และ Subnet Mask ให้กับ VLAN ที่เราสร้างขึ้นมา (ในที่นี้คือ VLAN 1000 ให้ IP 192.168.202.1/24)
~~~
interface Vlan-interface 100
ip address 192.168.202.1 255.255.255.0
quit
~~~
3. กำหนด Port ให้กับ VLAN (กำหนด port ที่ switch ต่อกับอุปกรณ์อื่น ในที่นี้กำหนด port GigabitEthernet 1/0/24 อยู่ใน VLAN 1000)
~~~
interface GigabitEthernet 1/0/24
port access vlan 1000
quit
save
~~~
## ข้อแตกต่างระหว่าง Untagged กับ Tagged VLAN
**Untagged VLANs (Access VLANs)**
- ในการส่งข้อมูลมีโครงสร้างแบบเส้นตรง เช่น ส่งผ่าน A ไป B มากกว่า A ไป B, C หรือ D
- วิธีการทำ เข้าไปที่ Interface ก่อน (`Interface GigabitEthernet x/0/x`) แล้วใช้คำสั่ง `port access vlan xxxx`
