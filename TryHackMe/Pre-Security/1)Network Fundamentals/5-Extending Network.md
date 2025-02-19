## **📌 1.Port Forwarding**
### **📌 Port Forwarding Nedir?**

Port forwarding, **yerel ağdaki (LAN) cihazların internete erişmesini** sağlayan bir yönlendirme yöntemidir. **Varsayılan olarak, bir ağ içindeki sunucular sadece yerel cihazlara hizmet verebilir.**

📌 **Örnek:**

- **192.168.1.10** IP’sine sahip bir web sunucusu, yalnızca aynı ağdaki cihazlarca erişilebilir.
- **Port forwarding uygulanırsa**, **82.62.51.70** gibi bir genel IP üzerinden internet kullanıcıları da erişebilir.

---

### **📌 Port Forwarding vs. Güvenlik Duvarı**

🔹 **Port forwarding**, **belirli portları açarak** internetten erişime izin verir.  
🔹 **Firewall (Güvenlik Duvarı)**, **bu portlara gelen trafiğin güvenli olup olmadığını** kontrol eder.

📌 **Port forwarding işlemi, yönlendirici (router) üzerinde yapılandırılır.**

🚀 **Özet:** **Port forwarding, yerel sunucuların internet üzerinden erişilebilir olmasını sağlar. Ancak, güvenlik risklerine karşı firewall ile birlikte kullanılması önerilir.**
## **📌 2.Firewalls 101**
### **📌 Firewall (Güvenlik Duvarı) Nedir?**

Firewall, **ağa giren ve çıkan trafiği kontrol eden bir güvenlik mekanizmasıdır**. Bir sınır güvenliği gibi çalışarak belirli kriterlere göre **veri trafiğini izin verir veya engeller**.

🔹 **İncelenen Kriterler:**

- Trafiğin **kaynağı** (hangi IP’den geliyor?)
- Trafiğin **hedefi** (hangi IP’ye gidiyor?)
- **Port** (örneğin, sadece **80 numaralı porta** izin verilebilir)
- **Protokol** (**TCP, UDP veya her ikisi** kontrol edilebilir)

---

### **📌 Firewall Türleri**

|**Kategori**|**Açıklama**|
|---|---|
|**Stateful**|**Bağlantının tamamını analiz eder**, kararları **dinamik** verir. Daha güvenlidir ancak **fazla sistem kaynağı** kullanır.|
|**Stateless**|**Tek tek paketleri inceler**, **statik kurallara** dayanır. Daha hızlı ve hafiftir ancak **daha az esnektir**.|

📌 **Stateful firewall’lar daha akıllıdır, ancak Stateless firewall’lar yoğun trafik saldırılarına (DDoS gibi) karşı daha etkilidir.**

🚀 **Özet:** **Firewall, ağ güvenliğini sağlayan bir filtredir. Stateful firewall daha kapsamlı, Stateless firewall ise daha hızlı ve hafiftir.**
## **📌 3. VPN Basics**
### **📌 VPN (Virtual Private Network) Nedir?**

VPN, **farklı ağlardaki cihazları internet üzerinden güvenli bir şekilde bağlayan bir teknolojidir**. **Şifrelenmiş bir tünel** oluşturarak, yalnızca VPN içindeki cihazların haberleşmesini sağlar.

📌 **Örnek:**

- **Şirket içi ofis ağlarını güvenli şekilde birleştirir.**
- **Halka açık Wi-Fi ağlarında veri koruması sağlar.**
- **Anonimlik sunarak, kullanıcı trafiğini ISP’lerden gizler.**

---

### **📌 VPN’in Avantajları**

|**Avantaj**|**Açıklama**|
|---|---|
|**Farklı lokasyonları bağlar**|Şirketler, farklı ofislerdeki sunuculara erişebilir.|
|**Gizlilik sağlar**|Trafik şifrelenerek veri dinlemeye karşı korunur.|
|**Anonimlik sunar**|İnternet trafiği maskelenir, takip edilmesi zorlaşır.|

---

### **📌 VPN Türleri ve Teknolojileri**

|**Teknoloji**|**Açıklama**|
|---|---|
|**PPP**|Şifreleme ve kimlik doğrulama sağlar, ancak yönlendirme yapamaz.|
|**PPTP**|Kolay kurulum, zayıf şifreleme. Çoğu cihaz destekler.|
|**IPSec**|Güçlü şifreleme, karmaşık kurulum. Çoğu modern cihazla uyumlu.|

🚀 **Özet:** **VPN, güvenli ve özel bir ağ bağlantısı sağlar. Farklı protokollerle çalışır ve hem gizlilik hem de veri güvenliği sunar.**
## **📌 4.LAN Networking Devices**

### **📌 Router Nedir?**

Router, **ağları birbirine bağlayan ve veri yönlendiren** bir cihazdır. **OSI modelinin 3. katmanında (Network Layer) çalışır** ve en iyi yolu belirleyerek veriyi iletir.

🔹 **Rota belirleme kriterleri:**

- **Kısa yol** (en az atlama noktası)
- **Güvenilir yol** (bağlantı stabilitesi)
- **Hızlı yol** (fiber > bakır)

📌 **Router, bir ağı internete veya başka bir ağa bağlayan temel cihazdır.**

---

### **📌 Switch Nedir?**

Switch, **birden fazla cihazı birbirine bağlayan** bir ağ cihazıdır. **Ethernet kablolarıyla 3 ila 63 cihaza kadar bağlantı sağlayabilir.**

🔹 **Switch Türleri:**

|**Tür**|**Açıklama**|
|---|---|
|**Layer 2 Switch**|**MAC adreslerini** kullanarak çerçeveleri yönlendirir.|
|**Layer 3 Switch**|Hem **çerçeve yönlendirme** hem de **IP paket yönlendirme** yapabilir.|

📌 **Layer 3 switch’ler, VLAN desteği sayesinde cihazları sanal olarak bölebilir.**

🚀 **Özet:** **Router ağları bağlar, switch cihazları bağlar. Layer 3 switch, bazı router işlevlerini yerine getirebilir.**