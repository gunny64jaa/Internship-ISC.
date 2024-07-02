# DHCP Server

## DHCP Server on access switch (HPE)
แจก IP ของ VLAN 100, 200 และ 300 บน Access Switch 
1. สร้าง DHCP ip-pool
```
sys
dhcp eneble
dhcp server ip-pool <x>
```
2. สร้าง network, gateway และ range (ตั้งแต่ .120 ถึง .200)
```
network 192.168.1.0 24
gateway-list 192.168.1.100
address range 192.168.1.120 192.168.1.200
```
3. วิธี check
```
dis dhcp server ip-in-use
```
4. ผลลัพธ์ที่ได้จาก LAB จริง
```
Pool name: 1
  Network: 192.168.1.0 mask 255.255.255.0 
  address range 192.168.1.120 to 192.168.1.200
  expired day 1 hour 0 minute 0 second 0
  gateway-list 192.168.1.100 
Pool name: 2
  Network: 192.168.2.0 mask 255.255.255.0 
  address range 192.168.2.120 to 192.168.2.200
  expired day 1 hour 0 minute 0 second 0
  gateway-list 192.168.2.100 
Pool name: 3
  Network: 192.168.3.0 mask 255.255.255.0 
  address range 192.168.3.120 to 192.168.3.200
  expired day 1 hour 0 minute 0 second 0
  gateway-list 192.168.3.100 
```
## DHCP Server on Fortigate Firewall
แจก IP ของ VLAN 400 และ 500 บน Firewall
1. ทดลบ
