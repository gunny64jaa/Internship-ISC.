# DHCP Server

## DHCP Server on access switch (HPE)
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
