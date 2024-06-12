# LACP

การทำ LACP เป็นการเพิ่มความเร็วในการส่งข้อมูล และ เพิ่ม Redundancy โดยการใช้ LAN cable 2 เส้นต่อขนานกัน (หากไม่มีการทำ LACP และมีการต่อ 2 เส้นใน switch จะเกิด Loop)
ขั้นตอนในการทำดังนี้
1. สร้าง Interface ของ LACP
~~~
sys
interface bridge-aggregation <id number>
link-aggregation mode dynamic
quit
~~~
2. เข้า port interface ที่เราต้องการจะทำ LACP
~~~
interface GigabitEthernet x/0/x
port link-aggregation group <id number>
~~~
3. ทำซ้ำกับ switch อีกตัวนึงที่เราต้องการทำ LACP
4. วิธีเช็ค
- เข้าไปที่ `display interface brief` จะเห็น port interface ที่เราทำขึ้นความเร็ว 2 Gb ทั้งคู่
- เข้าไปที่ `display bridge-aggregation` จะเห็น Group และ ความเร็วของทั้งสองอุปกรณ์
