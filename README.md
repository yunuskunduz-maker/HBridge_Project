# STM32 & H-Bridge DC Motor Control

***

### **PROJE ÖZETİ**
***Bu çalışma, endüstriyel standartlarda güvenlik ve kontrol prensipleriyle geliştirilmiş, STM32F103C8 tabanlı bir DC motor sürücü sistemidir.*** Projenin temel amacı; sadece bir motoru döndürmek değil, **savunma sanayii** ve **otomotiv** sektörlerinde (ASELSAN, TOGG vb.) kritik öneme sahip olan **Dead-Time (Ölü Zaman) yönetimi**, **Level Shifting (Seviye Kaydırma)** ve **Hardware Interlock (Donanımsal Kilitleme)** gibi ileri seviye mühendislik problemlerine çözüm üretmektir.

---

### 🚀 **TEKNİK ÖZELLİKLER**

* **Dinamik Hız Kontrolü (PWM):** STM32 Timer2 birimi üzerinden üretilen yüksek frekanslı sinyaller ile motor hızı %0-100 duty cycle aralığında hassas bir şekilde kontrol edilir.
* **Donanımsal Güvenlik (74HC08):** AND kapıları kullanılarak oluşturulan mantıksal kilitleme katmanı sayesinde, yazılımsal bir hata oluşsa dahi motorun iki yönünün aynı anda aktif olması (kısa devre) donanımsal olarak engellenmiştir.
* **Yazılımsal Ölü Zaman (Dead-Time):** Yön değişimleri sırasında transistörlerin tam kapanmasını sağlamak amacıyla algoritma içerisine 500ms güvenlik gecikmesi eklenerek "Shoot-through" akımları engellenmiştir.
* **İzole Güç Katmanı (Level Shifter):** 3.3V mikrodenetleyici sinyalleri, BC237 transistörleri üzerinden 12V güç katmanına kayıpsız ve izole bir şekilde aktarılmıştır.

---

### 🛠️ **TEKNİK SPEKTRUM**

#### **Donanım Mimarisi**
* **Mikrodenetleyici:** STM32F103C8T6 (ARM Cortex-M3).
* **Güç Transistörleri:** TIP122 (NPN) ve TIP127 (PNP) Darlington çiftleri.
* **Sürücü Katmanı:** BC237 NPN transistörlü seviye kaydırıcılar.
* **Lojik Koruma:** 74HC08 Quad AND Gates.
* **Koruma Elemanları:** 1N4007 Flyback diyotları (Ters EMF koruması).

#### **Yazılım Mimarisi**
* **Geliştirme Ortamı:** STM32CubeIDE.
* **Kütüphane:** STM32 HAL (Hardware Abstraction Layer).
* **Algoritma:** Modüler `Motor_Drive` ve `Motor_Stop` fonksiyonları ile sürdürülebilir kod yapısı.

---

### 📈 **SİMÜLASYON VE ANALİZ**

Sistem, **Proteus 8.13+** ortamında tam kapsamlı olarak test edilmiş ve sinyal kararlılığı dijital osiloskop üzerinden doğrulanmıştır.

![Devre Şeması](./Hardware/devre_semasi.png)
> **Görsel 1:** Tamamlanmış profesyonel devre şeması ve lojik koruma katmanı.

![Sinyal Analizi](./Hardware/sinyal_analizi.png)
> **Görsel 2:** %20 ve %80 Duty Cycle sinyal analizleri.
***

### 📁 **KLASÖR YAPISI**

* **/Firmware:** STM32CubeIDE kaynak kodları ve derlenmiş `.hex` dosyası.
* **/Hardware:** Proteus simülasyon projesi (`.pdsprj`).

---

### **İLETİŞİM**
**Yunus Kunduz** *Necmettin Erbakan Üniversitesi - Elektrik-Elektronik Mühendisliği (3. Sınıf)*

***
