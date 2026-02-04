# STM32 & H-Bridge DC Motor Control

Bu proje, **STM32F103C8** mikrodenetleyicisi ile bir **H-Köprüsü** sürücüsü kullanarak DC motorun hız ve yön kontrolünü gerçekleştirmektedir.

### 🛠️ Teknik Özellikler
* **Hız Kontrolü:** Timer2 üzerinden üretilen PWM sinyalleri ile hassas hız ayarı.
* **Güvenlik:** Yön değişimleri arasında **Dead-Time** (Ölü Zaman) koruması.
* **Donanım:** Seviye kaydırıcı (BC237) ve lojik kapı (74HC08) koruma katmanları.

### 📁 Klasör Yapısı
* `/Firmware`: STM32CubeIDE kaynak kodları.
* `/Hardware`: Proteus 8.13 simülasyon dosyaları.

---
*Bu proje **CozumLab** eğitim içerikleri kapsamında geliştirilmiştir.*