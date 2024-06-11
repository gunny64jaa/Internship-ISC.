# VLAN & IP

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
> ข้อแตกต่างระหว่าง Untagged กับ Tagged VLAN :
> test
