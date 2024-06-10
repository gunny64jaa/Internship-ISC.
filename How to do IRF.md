# How to do IRF
วิธีการทำ IRF ของ Switch HPE 5140

 - ใช้ Program SecureCRT 9.4 Version Crack
 - ใช้สาย Link ในการเชื่อม 2 Port
 - สาย Console ใช้ USB to LAN cable

ขั้นตอนดังนี้
1. ต่อ Console ของ Switch ตัวที่ 1 เข้าคอมพิวเตอร์ (กำหนด Port ที่เราจะใช้ ในที่นี้จะใช้ Port 25 และ 26)
2. Config switch ตัวที่ 1 ใน SecureCRT ดังนี้
~~~
system-view

interface Ten-GigabitEthernet1/0/25

shutdown

quit

#

interface Ten-GigabitEthernet1/0/26

shutdown

quit

#

irf-port 1/1

port group interface Ten-GigabitEthernet1/0/25

quit

#

irf-port 1/2

port group interface Ten-GigabitEthernet1/0/26

quit

#

irf-port-configuration active

#

interface Ten-GigabitEthernet1/0/25

undo shutdown

#

interface Ten-GigabitEthernet1/0/26

undo shutdown

#

save
~~~
3. ต่อ Console ของ Switch ตัวที่ 2 เข้าคอมพิวเตอร์ (กำหนด Port ที่เราจะใช้ ในที่นี้จะใช้ Port 25 และ 26)
4. Config switch ตัวที่ 2 ใน SecureCRT ดังนี้
~~~
system-view

irf member 1 renumber 2

y

save

y

quit

reboot

y

system-view

interface Ten-GigabitEthernet2/0/25

shutdown

quit

#

interface Ten-GigabitEthernet2/0/26

shutdown

quit

#

irf-port 2/1

port group interface Ten-GigabitEthernet2/0/26

quit

#

irf-port 2/2

port group interface Ten-GigabitEthernet2/0/25

quit

#

irf-port-configuration active

interface Ten-GigabitEthernet2/0/25

undo shutdown

#

interface Ten-GigabitEthernet2/0/26

undo shutdown

#

save
~~~
