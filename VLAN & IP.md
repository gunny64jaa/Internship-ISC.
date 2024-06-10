# VLAN & IP

1. การสร้าง VLAN ยกตัวอย่างเช่น ต้องการสร้าง VLAN 100
~~~
system-view
vlan 100
quit
~~~
2. การกำหนด IP Address และ Subnet Mask ให้กับ VLAN ที่เราสร้างขึ้นมา (ในที่นี้คือ VLAN 100 ให้ IP 193.168.201.1/24)
~~~
Vlan-interface 100
ip address 193.168.201.1 255.255.255.0
quit
~~~
