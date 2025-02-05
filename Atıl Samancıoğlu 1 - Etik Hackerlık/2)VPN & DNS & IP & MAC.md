
| Local IP                     | Public IP                        | MAC Adress                  |
| ---------------------------- | -------------------------------- | --------------------------- |
| Router atar                  | ISS atar                         | Cihaz seri numarası gibidir |
| Ağ içi iletişim              | Global iletişim                  |                             |
| 192... veya 10... ile başlar | IPv4'te 4 oktet, IPv6'da 8 oktet |                             |

- openvpn ...._vpn_....
- nano ...._vpn_....
	- tls -cipher "DEFAULT:@SECLEVEL=0"
- /etc/resolv.conf (DNS)

- **MAC DEĞİŞTİRME**
	- ipconfig wlan0 down/up
	- macchanger --help
	- macchanger --random wlan0 (down olmalı)
	- ifconfig wlan0 hw ether ...*newmac*... (2 karakter x 6 oktet)
	- service NetworkManager restart (sıfırlama)