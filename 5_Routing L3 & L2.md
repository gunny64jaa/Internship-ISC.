# Routing L3 & L2

จากแผนภาพที่อยู่ใน [Introduction ](https://github.com/gunny64jaa/Internship-ISC./blob/main/1_Introduction.md) ซึ่ง Core Switch สามารถ ping แล้วเจอ Firewall และ Access Switch ปกติได้แล้ว ขั้นตอนต่อไปเราต้องการให้ Firewall สามารถ ping ไปที่ Access Switch ปกติโดยผ่าน Core Switch ได้

1. เริ่มจากการสร้าง Routing จาก Access Switch ไป Core Switch โดยใช้คำสั่ง
```
system
ip route-static 0.0.0.0 0 192.168.100.1
save
```
สร้าง routing จาก Default ของ Access Switch ไป Gateway ของ Core Switch
2. สร้าง Routing จาก Core Switch ไป Fire Wall ใช้คำสั่งในทำนองเดียวกัน
```
system
ip route-static 0.0.0.0 0 192.168.254.60
save
```
สร้าง routing จาก Default ของ Core Switch ไป Gateway ของ Access Switch
3. สร้าง Static Route ใน Firewall ให้มี VLAN ของ Access Switch (ในที่นี้คือ VLAN 100)
```
1. เข้าไปที่ Network -> Static Route -> Create New
2. กรอกข้อมูล
- Destination : 192.168.100.0/255.255.255.0
- Gateway Access : 192.168.254.1
- VLAN : VLAN 1000 (VLAN ของ Core Switch)
```
