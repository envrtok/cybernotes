### **📌 1.Port Forwarding (Bağlantı Noktası Yönlendirme)**

🔹 **Port forwarding, yerel ağdaki (LAN) bir hizmeti internetten erişilebilir hâle getiren bir işlemdir.**  
🔹 Normalde bir web sunucusu **sadece aynı ağdaki cihazlar tarafından** erişilebilir (**intranet**).  
🔹 **Port forwarding ile, harici cihazlar (internet) bu hizmete ulaşabilir.**

---

#### **📌 Port Forwarding Nasıl Çalışır?**

1️⃣ **Yerel ağdaki bir cihaz (ör. 192.168.1.10) port 80’de bir web sunucusu çalıştırıyor.**  
2️⃣ **Bu cihaz, yalnızca aynı ağ içindeki diğer cihazlardan erişilebilir.**  
3️⃣ **Router’da port forwarding yapılandırılarak, gelen bağlantılar belirli bir cihaza yönlendirilir.**  
4️⃣ **Dış dünyadaki kullanıcılar artık "Public IP (Örn: 82.62.51.70:80)" üzerinden erişebilir.**

📌 **Özet:** **Port forwarding, belirli portları açarak internetten erişimi sağlar. Ancak, firewall'lar (güvenlik duvarları) gelen trafiği kısıtlayabilir.** 🔥
### **📌 2.Firewall (Güvenlik Duvarı) **

🔹 **Firewall, ağ trafiğini denetleyen ve filtreleyen bir güvenlik sistemidir.**  
🔹 **Hangi trafiğin geçeceğine veya engelleneceğine karar verir.**

---

#### **📌 Firewall Ne Kriterlere Göre Trafiği Denetler?**

✅ **Kaynak IP:** Trafik hangi ağdan geliyor?  
✅ **Hedef IP:** Trafik nereye gidiyor?  
✅ **Port Numarası:** Örneğin, sadece 80 (HTTP) portuna izin verilebilir.  
✅ **Protokol:** TCP, UDP veya her ikisini de filtreleyebilir.

🔥 **Örnek:** Bir web sunucusuna sadece **80 ve 443 portları** üzerinden bağlantıya izin verilirken, diğer tüm portlardan gelen bağlantılar engellenebilir.

---

#### **📌 Firewall Türleri**

|**Tür**|**Açıklama**|
|---|---|
|**Stateful Firewall**|**Bağlantının tamamını analiz eder.** Kararları daha akıllıdır ama daha fazla sistem kaynağı tüketir.|
|**Stateless Firewall**|**Her paketi tek tek değerlendirir.** Daha hızlı ama daha az güvenlidir. Önceden belirlenen kurallara dayanır.|

🔥 **Örnek:**

- **Stateful Firewall:** Eğer bir cihaz zararlı bağlantılar kuruyorsa, **tüm cihaz engellenir.**
- **Stateless Firewall:** Zararlı **tek bir paket** algılansa bile, diğer paketler etkilenmez.

📌 **Özet:** **Firewall, belirlenen kurallara göre trafiği kontrol eder ve tehditleri engeller. Stateful firewall daha güvenli ama kaynak tüketir, stateless firewall daha hızlı ama kural bazlıdır.** 🔥
### **📌3. VPN (Virtual Private Network)**

🔹 **VPN, internet üzerinden güvenli ve şifreli bir bağlantı oluşturarak uzak cihazların özel bir ağ gibi iletişim kurmasını sağlar.**  
🔹 **İki ayrı ağ (ör. iki farklı ofis) VPN ile birleşerek sanki aynı ağdaymış gibi çalışabilir.**

---

#### **📌 VPN’in Avantajları**

✅ **Uzak ağları birleştirir.**  
Örn: Farklı şehirlerdeki ofisler, VPN ile aynı ağdaymış gibi çalışabilir.

✅ **Gizlilik sağlar.**  
Veriler **şifrelenerek** gönderilir, böylece ağ dinleme (sniffing) saldırılarından korunur.

✅ **Anonimlik sağlar.**  
VPN kullanımı, ISS'lerin (İnternet Servis Sağlayıcılar) ve diğer aracıların trafiğini izlemesini zorlaştırır.

🔹 **Örn:** TryHackMe, makinelerine güvenli erişim sağlamak için VPN kullanır.

---

#### **📌 VPN Teknolojileri**

|**Teknoloji**|**Açıklama**|
|---|---|
|**PPP (Point-to-Point Protocol)**|Kimlik doğrulama ve veri şifreleme sağlar, ancak yönlendirme yapamaz.|
|**PPTP (Point-to-Point Tunneling Protocol)**|VPN tünelleme sağlar, kurulumu kolaydır ama zayıf şifrelemeye sahiptir.|
|**IPSec (Internet Protocol Security)**|IP üzerinden güçlü şifreleme sağlar, ancak kurulumu karmaşıktır.|

📌 **Özet:** **VPN, şifrelenmiş bir tünel oluşturarak güvenli ve özel bir ağ bağlantısı sağlar. İş yerleri, gizlilik isteyen kullanıcılar ve TryHackMe gibi platformlar için kritik öneme sahiptir.** 🔒🚀
### **📌 4.Router ve Switch**

🔹 **Router (Yönlendirici)** ve **Switch (Anahtar)**, ağ cihazlarını bağlamak için kullanılır ancak farklı görevleri vardır.

---

#### **📌 Router Nedir?**

✅ **Ağları birbirine bağlayan cihazdır.** (Örn: Ev ağı ↔ İnternet)  
✅ **Verinin en iyi yolu kullanarak hedefe ulaşmasını sağlar.**  
✅ **Layer 3 (Ağ Katmanı) üzerinde çalışır.**  
✅ **Port yönlendirme, firewall kuralları gibi ayarları yönetebilir.**

🔥 **Router, farklı ağları (IP adresleri farklı) birbirine bağlar ve en iyi rotayı belirler.**

---

#### **📌 Switch Nedir?**

✅ **Birden fazla cihazı aynı ağ içinde bağlar.**  
✅ **Layer 2 Switch:** **Sadece MAC adreslerine göre veri iletir.**  
✅ **Layer 3 Switch:** **MAC adreslerine ek olarak, IP adreslerini de kullanarak yönlendirme yapabilir.**

---

#### **📌 Layer 3 Switch & VLAN (Virtual Local Area Network)**

✅ **VLAN, aynı switch içindeki cihazları sanal olarak ayırarak güvenlik ve yönetim kolaylığı sağlar.**  
✅ **Örn:** **Muhasebe ve Satış Departmanı aynı switch’i kullanabilir ama birbirleriyle iletişim kuramaz.**

📌 **Özet:**

- **Router, farklı ağları bağlar ve yönlendirir.**
- **Switch, aynı ağ içindeki cihazları birbirine bağlar.**
- **Layer 3 switch, IP yönlendirmesi yaparak router’a yakın özellikler kazanır.** 🔥