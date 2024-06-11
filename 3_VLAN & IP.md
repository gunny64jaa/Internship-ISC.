# VLAN & IP

1. การสร้าง VLAN ยกตัวอย่างเช่น ต้องการสร้าง VLAN 100
~~~
system-view
vlan 100
quit
~~~
2. การกำหนด IP Address และ Subnet Mask ให้กับ VLAN ที่เราสร้างขึ้นมา (ในที่นี้คือ VLAN 100 ให้ IP 193.168.201.1/24)
~~~
interface Vlan-interface 100
ip address 192.168.204.1 255.255.255.0
quit
~~~
3. กำหนด Port ให้กับ VLAN (กำหนด port ที่ switch ต่อกับอุปกรณ์อื่น ในที่นี้กำหนด port GigabitEthernet 1/0/4 อยู่ใน VLAN 100)
~~~
interface GigabitEthernet 1/0/4
port access vlan 100
quit
save
~~~
