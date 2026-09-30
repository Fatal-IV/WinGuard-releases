<div align="center">

<img src="assets/logo.png" alt="WinGuard" width="112" />

# WinGuard

**Laptopunuza göz kulak olur.**
Windows 11 için hırsızlık uyarı uygulaması: siz uzaktayken cihazınıza dokunulursa ekranı kilitler, sirenle uyarır ve telefonunuza bildirim gönderir.

<br />

[![İndir](https://img.shields.io/badge/%E2%AC%87%20%C4%B0ND%C4%B0R-WinGuard--Setup.exe-0067C0?style=for-the-badge&logo=windows11&logoColor=white)](https://github.com/Fatal-IV/WinGuard-releases/releases/latest)

[![Son sürüm](https://img.shields.io/github/v/release/Fatal-IV/WinGuard-releases?style=flat-square&label=son%20s%C3%BCr%C3%BCm&color=0067C0)](https://github.com/Fatal-IV/WinGuard-releases/releases/latest)
[![İndirme](https://img.shields.io/github/downloads/Fatal-IV/WinGuard-releases/total?style=flat-square&label=indirme&color=2E9E6B)](https://github.com/Fatal-IV/WinGuard-releases/releases)
![Windows 11](https://img.shields.io/badge/Windows-11-0078D4?style=flat-square&logo=windows11&logoColor=white)
![Bildirim](https://img.shields.io/badge/bildirim-ntfy-57A5E0?style=flat-square)

<br />

<img src="assets/panel.png" alt="WinGuard paneli" width="860" />

</div>

<br />

## Ne yapar?

Korumayı başlattığınızda WinGuard bilgisayarınızı nöbete alır. Şarj kablosu çıkarılır, kapak kapatılır, USB takılır ya da klavyeye/fareye dokunulursa **tam ekran kilit** ve **PIN ekranı** açılır. PIN doğru girilmezse siren çalar ve telefonunuza anında bildirim gider.

| | |
|---|---|
| 🔌 **Beş sensör** | Şarj kablosu, ekran kapağı, USB, klavye/fare ve harici ekran. Hangilerinin açık olacağını siz seçersiniz. |
| 🖥️ **Tam ekran kilit** | Tüm monitörleri kaplar. Alt+Tab, Win tuşu ve benzeri kısayollar engellenir. |
| 🔐 **PIN ile açma** | Yanlış denemeler sınırlanır. PIN düz metin olarak saklanmaz. |
| 📱 **Telefona bildirim** | [ntfy](https://ntfy.sh) uygulamasıyla anlık bildirim. Sunucu kurmanız gerekmez. |
| 📷 **Kamera fotoğrafı** | İsteğe bağlı: uyarıda ve yanlış PIN'de fotoğraf çeker. Telefona gönderme ayrı bir anahtardır ve varsayılan olarak kapalıdır. |
| 🛡️ **Nöbet sertleştirmesi** | Nöbet sürerken Görev Yöneticisi, Ctrl+Alt+Del seçenekleri ve güç düğmesi kısıtlanır. |
| ⌨️ **Win+L ile başlat** | İsteğe bağlı: Win+L Windows'u kilitlemek yerine korumayı başlatır. |
| 🐕 **Bekçi süreci** | Uygulama kapatılmaya çalışılırsa arka planda yeniden başlatır. |
| ⚡ **Anında ya da geri sayımlı** | Korumayı hemen başlatabilir ya da kalkmanız için bir geri sayım ayarlayabilirsiniz. |

## Kurulum

1. [**Son sürümü indirin**](https://github.com/Fatal-IV/WinGuard-releases/releases/latest) (`WinGuard-Setup.exe`).
2. Çalıştırın ve yönetici iznini onaylayın. Kurulum tek tıktır.
3. WinGuard'ı açın, bir **PIN** belirleyin ve telefonunuzla QR kodu okutun.
4. Panelden **Korumayı başlat**'a basın.

> **Not:** Kurucu şu an bir geliştirici test sertifikasıyla imzalıdır. Windows SmartScreen bir uyarı gösterebilir; "Ek bilgi → Yine de çalıştır" ile devam edebilirsiniz. Güvenmek istemiyorsanız dosyanın özetini aşağıdaki gibi doğrulayabilirsiniz.

<details>
<summary><b>İndirdiğiniz dosyayı doğrulama</b></summary>

<br />

Her sürümde kurucunun yanında bir `WinGuard-Setup.exe.sha256` dosyası bulunur. PowerShell'de:

```powershell
(Get-FileHash .\WinGuard-Setup.exe -Algorithm SHA256).Hash
```

Çıkan değer `.sha256` dosyasındaki ile aynı olmalıdır.

</details>

## Telefon eşleştirme

WinGuard bildirimleri için ücretsiz **ntfy** uygulamasını kullanır (Android ve iOS).

1. Telefonunuza ntfy uygulamasını kurun. Kurulum sihirbazındaki ilk QR sizi doğru mağazaya götürür.
2. İkinci QR'ı okutun; uygulama sizin için rastgele oluşturulmuş kanala kendiliğinden abone olur.
3. Web sayfasını açık tutmanız gerekmez. Bildirimler uygulamaya arka planda gelir.

Kanal adı rastgele ve tahmin edilemezdir. İstediğiniz zaman **Ayarlar → Bildirim → Yeni QR oluştur** ile yeni bir kanal üretebilirsiniz; eski kanal geçersiz olur.

## Gizlilik ve güvenlik

- PIN düz metin olarak saklanmaz (özeti tutulur); bildirim kanal adı yalnızca sizin Windows hesabınızla çözülebilecek şekilde şifrelenir.
- Kamera fotoğrafları cihazınızda kalır. **Telefona gönder** açıksa fotoğraf, herkese açık bir sunucu olan ntfy.sh üzerinden iletilir; bu yüzden varsayılan olarak kapalıdır.
- Kamera çekimi sırasında kamera ışığı yanar; bunu gizlemek mümkün değildir.
- Bu depo yalnızca indirmeleri içerir. Kaynak kod herkese açık değildir.

## Sistem gereksinimleri

- Windows 11
- İnternet bağlantısı (telefon bildirimleri için)

## Bilinen sınırlar

- **Ctrl+Alt+Del** Windows tarafından yönetilir; uygulama bu kısayolu engelleyemez, yalnızca ekrandaki seçenekleri kısıtlar.
- Güvenli Mod ya da yönetici hesabı olan biri korumayı aşabilir. WinGuard bir güvenlik duvarı değil, caydırıcı bir uyarı sistemidir.

<br />

<div align="center">

**[⬇ Son sürümü indir](https://github.com/Fatal-IV/WinGuard-releases/releases/latest)** · [Tüm sürümler](https://github.com/Fatal-IV/WinGuard-releases/releases)

<sub>WinGuard © Fatal-IV</sub>

</div>
