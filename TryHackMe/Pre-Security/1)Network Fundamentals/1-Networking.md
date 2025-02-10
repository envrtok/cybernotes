- **Ping**: Bir bağlantının performansını veya güvenliğini test etmek için ICMP paketleri gönderilmesi.
## **1.1) IP Adresi Nedir?**

Bir **IP adresi (Internet Protocol Address)**, cihazların internette veya yerel ağda (LAN) birbirini tanıyabilmesi için kullanılan bir kimlik numarasıdır.

Bir IP adresi **4 sayıdan** oluşur ve her biri **0 ile 255** arasında olabilir. Örneğin:  
✅ **192.168.1.1**  
✅ **10.0.0.1**  
✅ **172.16.0.100**

Bu adreslerin her biri **32 bit** uzunluğundadır ve **noktayla ayrılmış 4 oktet** şeklinde gösterilir.
![[Pasted image 20250210172723.png]]
---

## **1.2) IP Türleri: Global (Genel) ve Local (Yerel) IP**

IP adresleri, **kapsamlarına** göre **Global (Genel) IP** ve **Local (Yerel) IP** olmak üzere ikiye ayrılır.

### **✅ Local (Yerel) IP Nedir?**

- Yerel ağdaki (LAN) cihazlara atanmış **özel** IP adresleridir.
- **Modem, router (yönlendirici) tarafından atanır.**
- **İnternete doğrudan çıkamaz**, sadece yerel ağ içinde geçerlidir.
- **Örnekler:**
    - **192.168.x.x**
    - **10.x.x.x**
    - **172.16.x.x – 172.31.x.x**

📌 **Gerçek Hayat Örneği:**  
Bir kafeye bağlandığında, telefonun yerel IP’si **192.168.1.5** olabilir. Ancak dış dünyaya bu IP ile değil, modemin Global IP’si ile çıkarsın.

### **✅ Global (Genel) IP Nedir?**

- İnternet Servis Sağlayıcı (ISS) tarafından atanır.
- İnternet üzerindeki **tüm dünyada benzersizdir**.
- **Web siteleri, online oyunlar, uzaktan bağlantılar için kullanılır.**
- **Örnek:** **85.120.45.32**

📌 **Gerçek Hayat Örneği:**  
Evinizde internete bağlandığınızda, bilgisayarınızın yerel IP’si **192.168.1.10** olabilir. Ama dış dünyada **85.120.45.32** gibi bir Global IP ile görünürsünüz.

---

## **1.3) IPv4 ve IPv6 Nedir?**

IP adresleri **IPv4** ve **IPv6** olarak ikiye ayrılır.

### **✅ IPv4 (Internet Protocol Version 4)**

- **En yaygın kullanılan IP sürümüdür.**
- **32 bit uzunluğundadır** ve **4 oktet** içerir.
- **Toplam 4.3 milyar adres** sağlayabilir.
- **Örnekler:**
    - **192.168.1.1**
    - **10.0.0.1**
    - **85.120.45.32**

📌 **Sorun:** İnternet büyüdükçe IPv4 adresleri **yetersiz** kalmaya başladı. İşte burada **IPv6** devreye giriyor!

### **✅ IPv6 (Internet Protocol Version 6)**

- **128 bit uzunluğundadır**, IPv4’ten çok daha fazla adres sağlar.
- **Hexadecimal (16’lık) sistem** kullanır.
- **Örnek:**
    - **2001:0db8:85a3:0000:0000:8a2e:0370:7334**
- **Güvenlik ve hız avantajları vardır.**

📌 **Gerçek Hayat Örneği:**  
Günümüzde birçok internet sitesi **hem IPv4 hem de IPv6 destekler**. Ama çoğu cihaz hâlâ **IPv4 kullanıyor.**

---

## **1.4) MAC Adresi Nedir?**

- **MAC Adresi (Media Access Control Address)**, her ağ kartına özel olarak üretilmiş **benzersiz** bir kimlik numarasıdır.
- **IP adresi değişebilir**, ama MAC adresi **sabit** kalır (sadece donanıma özeldir).
- **6 çift hexadecimal sayıdan** oluşur (toplam **48 bit**).

**Örnek:**  
✅ **00:1A:2B:3C:4D:5E**  
✅ **FC:34:97:5A:10:B2**

📌 **Gerçek Hayat Örneği:**

- Wi-Fi ağınıza sadece belirli cihazların bağlanmasını istiyorsanız, **MAC filtresi** ile izin verilen cihazları seçebilirsiniz.
- Bilgisayarın ağ kartı değişirse, MAC adresi de değişir.

