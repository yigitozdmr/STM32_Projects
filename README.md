# STM32_Projects
2. yaz stajı projelerim-Dora Makina
# Yazılımsal Timer ile LED Kontrol (STM32F4)

Bu proje, STM32F407 Discovery kartı üzerinde **HAL timer interrupt** kullanarak bir LED’in bloklamasız (non-blocking) yazılımsal timer ile belirli aralıklarla yakılıp söndürülmesini sağlamaktadır.

## Özellikler

* **Timer Interrupt Kullanımı:** HAL timer kesmeleri ile LED toggle işlemi.
* **Non-Blocking Zamanlama:** `HAL_Delay()` kullanılmadan, bloklamasız olay yönetimi.
* **Buton ile Duraklatma (isteğe bağlı):** Projeye kolayca eklenebilecek buton desteği.

## Gereksinimler

* **Donanım:**

  * STM32F407 Discovery kartı
  * USB micro-B kablo
  * LED (kart üzerindeki dahili LED)
* **Yazılım:**

  * STM32CubeIDE v1.xx
  * STM32CubeMX
  * Git (GitHub Desktop veya CLI)

## Proje Yapısı

```bash
led-timer-control/           # Proje kökü
├── Core/                    # `main.c` ve interrupt handler dosyaları
│   ├── Inc/                 # Header (.h) dosyaları
│   └── Src/                 # Kaynak (.c) dosyaları
├── Drivers/                 # HAL & CMSIS sürücüleri
│   ├── CMSIS/
│   └── STM32F4xx_HAL_Driver/
├── led_timer.ioc            # CubeMX konfigürasyon dosyası
├── .gitignore               # Git ignore kuralları
└── README.md                # Proje tanıtımı
```

## Kurulum ve Kullanım

1. **Repoyu Klonlayın:**

   ```bash
   git clone https://github.com/kullaniciAdin/led-timer-control.git
   cd led-timer-control
   ```
2. **STM32CubeIDE ile Açın:**

   * `led_timer.ioc` dosyasını çift tıklayarak proje ayarlarını gözden geçirin.
   * Projeyi "Build" ile derleyin.
3. **Kartı Bağlayın ve Çalıştırın:**

   * USB kablo ile Discovery kartınızı PC’ye bağlayın.
   * STM32CubeIDE’de "Run" seçeneği ile kodu karta yükleyin ve başlatın.
4. **LED Davranışını Gözlemleyin:**

   * LED her timer interrupt tetiklendiğinde yanıp sönecektir.

## README Görseli (Opsiyonel)

![LED Timer Demo](led_timer_demo.jpg)

> *Proje çalışırken LED’in 1 saniye aralıklarla yanıp söndüğü demo görüntüsü.*

## .gitignore

README dosyanızın yanında aşağıdaki `.gitignore` dosyasını bulundurun:

```gitignore
# STM32CubeIDE / STM32CubeMX
/build/
Debug/
Release/
*.bin
*.elf
*.hex
*.o
*.d
*.log
*.launch
*.dep
*.cproject
*.project
.settings/
.metadata/
*.ioc-backup
MX_*
```

## Lisans

Bu proje MIT lisansı ile lisanslanmıştır. Detaylar için [LICENSE](LICENSE) dosyasına bakabilirsiniz.

---

*Hazırlayan: Yiğit Özdemir*
