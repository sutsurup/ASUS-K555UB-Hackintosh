# ASUS K555UB XO092T | Intel® Core™ i5 (6. Nesil)

[![macOS](https://img.shields.io/badge/macOS-10.15.7-orange)](https://www.apple.com/am/macos/catalina/)
[![OpenCore](https://img.shields.io/badge/Clover-5.1-9cf)](https://github.com/CloverHackyColor/CloverBootloader)
[![release](https://img.shields.io/badge/indir-son%20sürüm-blue.svg)](https://github.com/sutsurup/ASUS-K555UB-Hackintosh/releases)

<img align="right" src="Images/logo.png" alt="ASUS" width="200">

Türkçe | [English](https://github.com/sutsurup/ASUS-K555UB-Hackintosh/blob/master/README_EN.md)

**macOS Versiyonu: 10.15.7**

**Clover Versiyonu: v5.1 r5129**

**Desteklenen diğer K555UB modelleri:** XO066T/XO093T/XO096T/XO097T/XO198T/XO266T/XO099D/XO227D

# Detaylar

    Tarih:        5 Haziran, 2020
    Durum:        Stabil
    Destek:       BIOS (Sürüm 304)
    Yapı:         Clover Bootloader kullanılarak, sutsurup tarafından ASUS K555UB cihaza uyarlanmıştır

![Alt text](Images/Hackintosh.png)

## Donanım

| ║▌║ **ASUS** ║▌║ | Detay                                                  |
| ------------------- | ------------------------------------------- |
| Model Ismi      | K555UB XO092T      |
| Anakart           | X555UB     |
| CPU              | Intel(R) Core(TM) i5-6200U CPU @ 2.30GHz (max. 2.80GHz) Skylake-U              |
| RAM           | X555UB 4GB 1600 MHz DDR3 + Samsung 8GB 1600MHz DDR3    |
| Dahili Grafik Kartı | Intel(R) HD Graphics 520 (1 GB)                     |
| Wi-Fi             | Realtek RTL8723BE Wireless LAN 802.11n PCI-E |
| Kamera          | ASUS USB2.0 VGA UVC WebCam           |
| Ses       | Realtek ALC256 (Apple ALC Layout: 28)                        |
| Touchpad       | ELAN 1000                        |
| BIOS Versiyonu      | X555UB.304 (Sürüm 304)                   |

# Değiştirilen donanım(lar)

    HGST Travelstar 2.5-Inch 1TB 5400RPM | https://amzn.to/2LFlFMe
    Realtek RTL8723BE Wireless LAN 802.11n PCI-E
    
    
    Sebebi: SSD Yükseltmesi (Hız bakımından)
    Sebebi: Apple, RTL8723BE wireless kartını desteklemiyor

| Ürün    | Bilgi |
| ------------- | ------- |
| Samsung SSD 860 EVO 500GB   | https://amzn.to/2z9ef17   |
| James Donkey JD120 120GB   | https://bit.ly/2ZisP0W   |
| Dell DW1510 Wireless Kart Chip: BCM4322   | https://bit.ly/2yXeyMi   |

> II. SSD, cihaza DVD-RW sürücüsü söküldükten sonra takılmıştır. Gerekli parça: DVD to HDD aparatı (https://amzn.to/2Tdf1B5 benzeri) satın alarak içerisine HDD veya SSD donanımı yerleştirdikten sonra DVD-RW portuna takabilirsiniz.

> Dell DW1510, High Sierra ve Mojave gibi macOS sürümlerinde yerleşik olarak destekleniyor. Bu kartı satın alırsanız, Tak-Çalıştır yöntemiyle kullanabilirsiniz. Fakat bu kartın desteği, Catalina yayınlandığında son buldu. Kartı Catalina'da çalıştırabilmek için, High Sierra veya Mojave sisteminde /System/Library/Extensions klasöründeki IO80211Family.kext ve IO80211FamilyV2.kext dosyalarını çıkarmak ve Catalina'da yine aynı dizine kurmak gerekiyor. Bu dosyaları Mojave sisteminden çıkardım ve Releases bölümünde V1.1 altına paylaşıyorum. Kurulum sonrası bölümünde bu dosyaları nasıl yükleyeceğinizi anlattım.

# Desteklenmeyen donanımlar

    1. Harici Ekran Kartı (NVIDIA GeForce 940M PCI-e) [Apple desteklemiyor]
    2. 'FN + medya kontrolü' fonksiyon tuşları [Yama yapıldı - çalışıyor]
    4. ELAN1000 Touchpad [Yama yapıldı - çalışıyor]
    4. Realtek RTL8723BE Wireless (Wi-Fi kartı) [Apple desteklemiyor] -Yazının devamında çözümü var-

## Uyumluluk
Paylaştığım EFI klasörü, **macOS Catalina 10.15.7** sürümününe kadar desteklenmektedir.
macOS Mojave 10.14.6 sürümünü kuracaksanız, USB bellekteki EFI diskinde sırasıyla EFI > Clover > Kexts > 10.15 içerisindeki tüm dosyaları, bir üst dizindeki 10.14 klasörüne taşıyın. macOS High Sierra 10.13.6 için 10.13 klasörüne taşıyın.

## Yedeklerinizi alın
**Yükleme talimatlarına geçmeden önce;** Sistemde kurulu Windows, Linux veya benzeri bir işletim sistemi var ise her ihtimale karşı **önemli yedeklerinizi almayı unutmayın.** Yanlış diski silme veya diski **APFS formatlama** esnasında disk yapısı bozulabilir. Yedeklerinizi [Yandex.Disk](https://disk.yandex.com.tr) tarzı çevrimiçi bir depolama alanına veya (var ise) harici diskinize depolamanızı öneririm.

## Kurulum öncesi yapılması gerekenler
* [Etcher](https://www.balena.io/etcher/) programının işletim sisteminize uygun olan versiyonunu indirin
* KaoS tarafından paket haline getirilen, macOS kurulumu için gerekli olan RAW kurulum dosyasını ([OSXINFO sitesinden](https://osxinfo.net/konu/macos-catalina-amd-intel-kurulum-imaji.10455) indirin | Link konunun alt tarafındadır
* Paylaştığım son EFI.zip dosyasını indirin: [ASUS-K555UB-Hackintosh/releases/1.2](https://github.com/sutsurup/ASUS-K555UB-Hackintosh/releases)

# macOS Yükleme Talimatları


1. BIOS ekranına girin ve aşağıdaki değerleri değiştirin (ESC tuşu BIOS menüsüne girmeye yardımcı olur):

	- Display memory: 64MB
	- Intel® Virtualization Technology devre dışı bırak
	- Secure Boot devre dışı bırak
	- önerilir: Boot menüsünde USB belleği birinci tercih olarak seçin (En üstteki seçenek)

2. macOS kurulumunu başlatabilmek için USB belleğinize MAC kurulum dosyasını (RAW) Etcher programı yardımıyla yazdırın
3. İndirdiğiniz EFI.zip dosyasına sağ tıklayıp klasöre çıkarın. USB belleğin EFI diskindeki EFI klasörü içerisindeki BOOT ve CLOVER klasörlerini silin, indirdiğiniz EFI klasöründekileri oraya yükleyin
4. USB belleği takın, cihazı başlatın ve başlatma düğmesine basar basmaz ESC tuşuna basın. USB belleği seçerek devam edin ve macOS installer'ı seçin
5. Toucpad çalışacaktır - veya USB Mouse kullanabilirsiniz
6. macOS sistemini Windows yanına kuracaksanız, [bu rehber'de yapıldığı gibi](https://www.youtube.com/watch?v=nvXew__fuQE) Apple HFS diski oluşturmanız gerekiyor. Kurulum aşamasında bu diski seçerek ilerleyeceksiniz.
5. Cihazda sadece macOS kullanacaksanız, kurulum ekranı geldiğinde "Disk Izlencesi" bölümüne gidin, sol üstteki "Görüntü" yazısının üzerindeki butona basın ve tüm diskleri göster deyin. Bu sayede alt tarafta HDD/SSD donanımınız gözükecek. "Samsung SSD" gibi. Buna tıklayın ve sonrasında sağ tarafta bulunan "Sil" butonuna tıklayın. Biçim olarak "APFS", Düzen olarak "GUID Bölüntü Haritası" seçeceksiniz ve tekrar sil deyin. Işlem tamamlandığı zaman bu pencereyi kapatın ve kuruluma normal şekilde devam edin, yeni oluşturduğunuz APFS diskini seçin. Kurulum bittikten sonra cihaz yeniden başlayacaktır. Son yaptığınız işlemden sonra artık "macOS installer" seçmeyeceksiniz. Yeniden başladığı zaman 4. adımda yaptığınız gibi tekrar USB belleği seçin ve bu sefer yeni oluşturduğunuz APFS diskini seçin.  Bilgisayar her yeniden başladığında, yeni oluşturduğunuz APFS diski seçeceksiniz.  Kurulumun kalan kısmı bittiği zaman sistem kullanıma hazır hale gelecektir.

Sistemi yeni kurduğunuzdan dolayı ilk birkaç açılışta kendi içinde ayarlarını yapmaktadır. Bu sebeple yavaş açılabilir.
Sabırlı olun.
```
$ Destek almak için paylaştığım mail adresinden veya issue açarak bana ulaşabilirsiniz.
``` 

# Kurulum sonrası yararlanabileğiniz rehber/araçlar
* önerilir: iCloud'a giriş yapacaksanız veya iMessage, FaceTime kullanmak istiyorsanız, bu rehberi harfiyen uygulayın: [Hackintosh Cihazlarda iMessage Etkinleştirmek](https://osxinfo.net/konu/hackintosh-cihazlarda-imessage-etkinlestirmek.84)
* [Clover Configurator](https://mackie100projects.altervista.org/download-clover-configurator/)
* Hackintool ([Forum thread](https://www.insanelymac.com/forum/topic/335018-hackintool-v286/) | [Direkt indirme linki](http://headsoft.com.au/download/mac/Hackintool.zip))
* Kext Updater ([Indir](https://bitbucket.org/profdrluigi/kextupdater/downloads/) | [Forum](https://www.hackintosh-forum.de/forum/thread/32621-kext-updater-neue-version-3-x/) {Alman})

### Dell DW1510 wireless kartı Catalina'da nasıl çalıştırılır?
Daha öncesinde Dell DW1510 wireless kartının Catalina'da desteklenmediğini söylemiştim. Releases bölümünde V1.1 ile paylaştığım [Mojave-IO80211Family.zip](https://github.com/sutsurup/ASUS-K555UB-Hackintosh/releases/tag/1.1) dosyasını indirin.

1. [cVad's MAC] (http://cvad-mac.narod.ru/index/0-4) sitesinden Kext Utility uygulamasını indirin (Mavi ok işaretine basın)
2. Kext'leri sisteme yükleyebilmek için SIP devre dışı bırakmamız gerekiyor, Terminal'i açın, belirteceğim kodları sırayla yazın:
	- sudo -s (Sonrasında Password soracak, MAC'in şifresini girin)
	- spctl --master-disable
	- mount -uw /
	- killall Finder
3. Indirdiğiniz Kext Utility uygulamasını, Uygulamalar klasörüne taşıyın ve çalıştırın
4. Çalıştırdıktan sonra "Enjoy" yazısını görene kadar bekleyin
5. Mojave-IO80211Family.zip içerisindeki IO80211Family.kext ve IO80211FamilyV2.kext dosyalarını uygulamanın üzerine sürükleyin ve izin verin
6. Tekrar "Enjoy" yazısı gelene kadar bekleyin, kurulum tamamlanmıştır
7. Cihazı yeninden başlatın ve Wi-Fi'ın keyfini çıkarın :)

# Wi-Fi nasıl kullanırım?
K555UB sistemiyle yerleşik gelen Realtek RTL8723BE Wireless kartı Apple tarafından **deskteklenmediğinden dolayı,** bu kartı değiştirmeniz gerekiyor. Peki bu konuda ne yapabiliriz?

1. Anakart Half Mini PCI-e kartları desteklemektedir. Bu sebeple **kesinlikle** Mini PCI-e değil, Half Mini PCI-e kartlara yönelmelisiniz.
2. Bluetooth ve beraberinde AirDrop gibi macOS fonksiyonların çalışmasını istiyorsanız, +Bluetooth destekleyen kartları tercih edin.
3. Kablosuz USB Adaptör satın alabilirsiniz. Ben şu anda [ASUS Kablosuz N150 USB Nano Adaptör](https://www.asus.com/tr/Networking/USBN10_NANO) kullanmaktayım.

 AliExpres üzerinden Broadcom DW1510 ve Atheros AR5BHB92 kartları sipariş ettim. **Geldiği zaman bir test yaparız :)**
 Ayrıca: AzureWave AW-CB160H başta olmak üzere, AW-CE123H bu iki kartı öneririm.
 Düzenleme 05/10/2020: DW1510 wireless kartı geldi, 18 Lira vergisi ile birlikte :) Donanıma dahil edilmiştir

## Kablosuz USB Adaptörleri sisteme nasıl tanıtabilirsiniz?

Paylaşacağım kurulum dosyasının çalıştırdığı Kablosuz USB Adaptörler burada listelenmiştir:
[chris1111/Wireless-USB-Adapter-Clover](https://github.com/chris1111/Wireless-USB-Adapter-Clover)

1. Yayınlanan son sürümü buradan: [Wireless-USB-Adapter-Clover/Releases](https://github.com/chris1111/Wireless-USB-Adapter-Clover/releases), veya direk bu linke tıklayarak indirebilirsiniz. [Wireless-USB-Adapter-Clover/V14.zip](https://github.com/chris1111/Wireless-USB-Adapter-Clover/files/4301774/Wireless.USB.Adapter.Clover-V14.zip)  
2. Kurulum dosyasını indirikten sonra kurulumu tamamlayın  
3. Cihazı yeniden başlatın 
```
$ ASUS Kablosuz N150 USB Nano Adaptör için orijinal ASUS yazılım dosyası aşağıdadır:  
```  
1. [USB-N10 NANO // Sürücüler & Araçlar](https://www.asus.com/tr/Networking/USBN10_NANO/HelpDesk_Download/) 
2. Alternatif olarak, repo içerisinde "Wi-Fi Fix" klasöründe paylaştığım PKG dosyasını da yükleyebilirsiniz.

> Son bahsettiğim PKG dosyasını paylaşmamın asıl sebebi; Diğer bahsettiğim chris1111 ve ASUS orijinal kurulum dosyalarına nazaran sinyal göstergesinin çalışmasıdır. Diğerlerinde durum çubuğunda sembolik bir (sabit) Wi-Fi ikonu bulunur, sinyal çekim gücünü ancak listeye girince görebilirsiniz fakat "Wi-Fi Fix" klasöründeki kurulum dosyasıyla birlikte gelen durum çubuğundaki Wireless çekim gücü ikonu hareketlidir, çekim gücünü net gösterir.

## İletişime geçin
Website: https://sutsurup.com //
Mail: [contact@sutsurup.com](mailto:contact@sutsurup.com)

## Diğer bağlantılar
- [ASUS Resmi Websitesi // K555UB](https://www.asus.com/tr/Laptops/K555UB)
- [High Sierra 10.13](https://osxinfo.net/konu/basarili-kurulum-asus-k555ub-xo092t-mojave-10-14.6632)
- [Mojave 10.14](https://osxinfo.net/konu/basarili-kurulum-asus-k555ub-xo092t-mojave-10-14.6632)
- [Catalina 10.15.3](https://osxinfo.net/konu/asus-k555ub-xo092t-catalina-10-15-3.13141)
- [Clover Bootloader](https://github.com/CloverHackyColor/CloverBootloader/releases)

## Destek olun.
Projeyi faydalı bulduysanız, kaynak bulma konusunda bana yardımcı olmak için bağış yapabilirsiniz:
```
₿ 1Q8CEMHTuecxPUJpEdpRiG6Bg2GVtzw4bN
Papara ➜ 1801475764
``` 
<a href='https://github.com/sutsurup/sutsurup/blob/main/Donate.md'><img alt='Bağış' src='https://github.com/sutsurup/MSI-Hackintosh-Build/blob/main/Images/donate.png?raw=true' height='360px' width='375px'/></a>
```
QR kodu tarayarak alternatif seçeneklere ulaşabilirsiniz
``` 

### Teşekkürler:
**LeeBinder** (README.md örnekleri), **RehabMan** (ACPI hotpatch), ve **Hackintosh** sistemlere destek veren birçok kişiye...

Kolay gelsin!
