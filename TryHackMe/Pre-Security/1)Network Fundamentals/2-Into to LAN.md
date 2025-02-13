### **📌 1. LAN Topolojileri (Ağ Yapıları)**

Farklı ağ bağlantı türleri:

🔹 **Star (Yıldız) Topoloji**

- **Her cihaz merkezi bir cihaza bağlanır.**
- Yeni cihaz eklemek kolaydır, ancak merkez cihaz bozulursa tüm ağ gider.

🔹 **Bus (Omurga) Topoloji**

- **Tüm cihazlar tek bir kabloya bağlıdır.**
- **Kurulumu ucuz ve kolaydır**, ancak kablo hasar görürse tüm ağ çöker.

🔹 **Ring (Halka) Topoloji**

- **Veriler bir döngü içinde dolaşır.**
- Veri kaybı olmaz ama **tek bir hata tüm ağı çökertebilir.**

🔹 **Switch ve Router Farkı**

- **Switch**, cihazları birbirine **yerel** olarak bağlar. (Örneğin: Ofis içindeki PC’ler)
- **Router**, farklı ağları birbirine bağlar (Örneğin: Evdeki modem → İnternet)

---

### **📌 2. Subnetting (Alt Ağ Bölme İşlemi)**

**Subnetting**, büyük ağları **daha küçük parçalara bölerek** yönetimi kolaylaştırır.

🔹 **Örnek:**

- **192.168.1.0/24** → Muhasebe
- **192.168.2.0/24** → IT Departmanı
- **192.168.3.0/24** → Müşteri Wi-Fi

✅ **Ağ trafiğini azaltır, güvenliği artırır.**

🔹 **Subnet Mask (Alt Ağ Maskesi) Nedir?**  
Bir IP adresinde hangi kısmın **ağ**, hangi kısmın **cihaz** olduğunu belirler.

- **255.255.255.0** → **Ağ:** 192.168.1, **Cihaz:** .1 - .254
- **255.255.0.0** → **Ağ:** 192.168, **Cihaz:** 0.0 - 255.255

📌 **Özet:** **Subnetting ile ağ daha verimli ve güvenli hâle getirilir.**

---

### **📌 3. ARP (Address Resolution Protocol)**

- **ARP**, **IP adreslerini MAC adresleriyle eşleştiren** bir protokoldür.
- Bir cihaz, **"Bu IP kime ait?"** diye **ARP Request (istek) atar**.
- Hedef cihaz, **"Bu IP benim!"** diye **ARP Reply (cevap) yollar.**

🚀 **Özet:** **Ağ içindeki cihazlar, birbirlerini MAC adresleri ile bulur.**

---

### **📌 4. DHCP (Dynamic Host Configuration Protocol)**

**DHCP, cihazlara otomatik olarak IP adresi atayan sistemdir.**

🔹 **DHCP Süreci:**  
1️⃣ **DHCP Discover:** Cihaz IP adresi ister.  
2️⃣ **DHCP Offer:** DHCP sunucusu kullanılabilir IP’leri listeler.  
3️⃣ **DHCP Request:** Cihaz bir IP adresi seçer.  
4️⃣ **DHCP ACK:** DHCP sunucusu IP kullanımını onaylar.

🚀 **Özet:** **DHCP, IP adreslerini manuel girmeye gerek kalmadan otomatik dağıtır.**

---

📌 **Tüm konuların özeti:**

- **LAN topolojileri**, ağların nasıl kurulduğunu belirler.
- **Subnetting**, ağı daha küçük ve yönetilebilir parçalara böler.
- **ARP**, cihazların MAC adreslerini bulmasını sağlar.
- **DHCP**, IP adreslerini otomatik olarak dağıtır.