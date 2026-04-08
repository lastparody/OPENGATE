<br>
<div id="türkçe"></div>

<p align="center">
  <a href="#_">
    <img src="https://raw.githubusercontent.com/lastparody/OPENGATE/main/.github/images/logo.svg" width="320" alt="OpenGate Logo">
  </a>
</p><br>

<p align="center">
  <a href="https://ozkantanrikulu.com" target="_blank" rel="noopener noreferrer"><img src="https://img.shields.io/badge/Powered%20by-Özkan%20Tanrıkulu-1e6eb5?style=plastic" alt="Powered by Özkan Tanrıkulu"></a>&nbsp;&nbsp;<a href="#"><img src="https://img.shields.io/badge/version-1.0.3-e94560?style=plastic" alt="Version"></a>&nbsp;&nbsp;<a href="#"><img src="https://img.shields.io/badge/macOS-14.0+-000000?style=plastic" alt="macOS"></a>&nbsp;&nbsp;<a href="#"><img src="https://img.shields.io/badge/Silicon%20%26%20Intel-compatible-cd7700?style=plastic" alt="Architecture"></a>&nbsp;&nbsp;<a href="#"><img src="https://img.shields.io/badge/license-Proprietary-9b59b6?style=plastic" alt="License"></a>&nbsp;&nbsp;<a href="https://virustotal.com/gui/file/48d0ed815c7a0c738ff047da4a81f33deb479abfd28516b7652a0f8746f6edbc" target="_blank" rel="noopener noreferrer"><img src="https://img.shields.io/badge/VirusTotal-Clean-brightgreen?style=plastic&logo=virustotal&logoColor=white" alt="VirusTotal"></a>
</p> <br>


---

## OpenGate Nedir?

OpenGate, DPI bypass ve sansür atlatma için yerel bir macOS uygulamasıdır. Yüksek performanslı Go çekirdeği üzerine inşa edilmiştir. SNI parçalaması, TCP segmentasyonu ve DNS-over-HTTPS aracılığıyla internet servis sağlayıcılarının kısıtlamalarını atlatır. Çok katmanlı paket bölme teknikleriyle derin paket incelemeyi (DPI) devre dışı bırakır. Tek butonla çalışan sade bir arayüz, teknik bilgi gerektirmeyen kullanıcı dostu yapı.

---

## Özellikler

- **SNI Parçalaması** — Ana makine adı tabanlı filtrelemeyi önlemek için TLS Client Hello paketlerini böler.
- **TCP Segmentasyonu** — Durum bilgisi olan DPI motorlarının kafasını karıştırmak için TCP akışlarını küçük segmentlere ayırır.
- **DNS-over-HTTPS (DoH)** — Tüm DNS sorgularını HTTPS üzerinden şifreleyerek DNS tabanlı engellemeleri ve gözetimi ortadan kaldırır.
- **Otomatik Sistem Proxy'si** — Tek bir tıklamayla tüm macOS ağ trafiğini bypass çekirdeği üzerinden yönlendirir.
- **Yerel Ağ Yayını** — Mac'inizi bir proxy sunucusuna dönüştürerek DPI korumasını yerel ağınızdaki her cihaza genişletir.
- **Girişte Başlat** — Oturum açtığınızda korumayı otomatik olarak etkinleştirir.
- **Apple Silicon & Intel** — Her iki mimaride native çalışır.

---

## Performans

OpenGate düşük kaynak tüketimiyle çalışacak şekilde tasarlanmış ve optimize edilmiştir.

| Metrik | Değer |
|--------|-------|
| RAM Kullanımı | ~20 MB |
| CPU Kullanımı | <%0,1 |
| Pil Etkisi | Minimal |
| Ağ Performansı  | Bant genişliği korunur |
| İlk Bağlantı Gecikmesi | + 30–150 ms |

> SNI parçalaması, yalnızca her yeni bağlantı kurulumundaki el sıkışma aşamasında 30–150 ms'lik bir gecikmeye neden olur; bağlantı sağlandıktan sonraki tüm veri akışı herhangi bir performans kaybı olmaksızın tam hızda gerçekleşir.

---

## Kurulum

1.  En güncel `OpenGate.zip` dosyasını [Releases](https://github.com/lastparody/opengate/releases) sayfasından indirin.
2.  ZIP dosyasını açın ve içindeki **OpenGate.app** dosyasını **Uygulamalar** klasörüne sürükleyin.
3.  Uygulamayı ilk kez açtığınızda macOS bir güvenlik uyarısı gösterecektir. Bu durumda:
      - İletişim kutusundaki **"Tamam"** butonuna basarak pencereyi kapatın.
      - Mac'inizde **Sistem Ayarları → Gizlilik ve Güvenlik** (System Settings → Privacy & Security) bölümüne gidin.
      - En alta kaydırarak **"Yine de Aç"** butonuna tıklayın.
      - Tekrar sorulduğunda şifrenizi girin veya Touch ID kullanarak açın.

> OpenGate Apple tarafından onaylı değildir. Bu durum bağımsız geliştirilen açık dağıtımlı yazılımlar için standart bir prosedürdür. Uygulama herhangi bir zararlı kod içermemektedir ve gösterilen uyarı standart bir macOS protokolüdür.

---

## Kullanım

1. Uygulamalar klasöründen OpenGate'i çalıştırın.
2. Bağlantıyı kurmak için **kalkan simgesine** tıklayın.
3. Koruma aktifleştiğinde simge yeşil renge dönecektir.
4. Artık tüm internet trafiğiniz OpenGate aracılığıyla iletilmektedir.

---

## Ayarlar

| Ayar | Açıklama |
|---------|-------------|
| Yerel Ağ Geçidi | Bypass tüneli için IP adresi (varsayılan: 127.0.0.1) |
| DNS Adresi | DNS çözümleyici adresi (varsayılan: 8.8.8.8) |
| Bağlantı Portu | Atlatma çekirdeği için yerel port (varsayılan: 9090) |
| Güvenli DNS DoH | DNS sorgularını HTTPS üzerinden şifreler |
| IPv4 Önceliği | Maksimum kararlılık için DNS çözümlemesini IPv4'e zorlar |
| Ağ Kapsamı | Sistem geneli veya uygulama tabanlı proxy modu |
| Proxy Yayını | Korumayı ağınızdaki diğer cihazlarla paylaşın |
| Başlangıçta Çalıştır | Oturum açtığınızda otomatik bağlanır |

---

## SSS

**❓ OpenGate internetimi yavaşlatır mı?**
- Hayır. Bant genişliği üzerinde herhangi bir performans kaybına yol açmaz. SNI parçalaması nedeniyle yalnızca her yeni bağlantı kurulumunda 30–150 ms'lik bir gecikme yaşanır; bağlantı kurulduktan sonraki tüm veri akışı tam hızda devam eder.

**❓ Şarjımı tüketir mi?**
- Hayır. Go çekirdeği olay odaklıdır ve boşta olduğunda uyku moduna geçer. Normal çalışma sırasında CPU kullanımı **%0.1**'in altında kalır.

**❓ Ne kadar RAM kullanır?**
- Yaklaşık **20 MB** seviyesindedir. Bellek kullanımı stabildir ve kullanım süresi arttıkça yükselmez.

**❓ Uygulamayı açık tutmam gerekiyor mu?**
- Evet. Oturum açıldığında otomatik olarak başlatmak için ayarlardan **Başlangıçta Çalıştır** seçeneğini etkinleştirin.

**❓ Aynı ağdaki diğer cihazlarda kullanabilir miyim?**
- Evet. Ayarlardan **Proxy Yayını** seçeneğini etkinleştirin, ardından hedef cihazı manuel olarak yapılandırın.

**❓ Trafiğim kayıt altına alınıyor mu (loglanıyor mu)?**
- Hayır. OpenGate tamamen kendi cihazınızda çalışır, hiçbir harici sunucuya veri gönderilmez.
  
---

## Lisans

Bu yazılım kapalı kaynak bir projedir. Kullanım şartlarının tamamı için lütfen [LICENSE](https://github.com/lastparody/opengate/blob/main/LICENSE) dosyasına bakın.

<br><br>
<hr style="height:6px; border:none; color:#333; background-color:#333;">
<br><br>

<div id="english"></div>

<p align="center">
  <a href="#_">
    <img src="https://raw.githubusercontent.com/lastparody/OPENGATE/main/.github/images/logo.svg" width="320" alt="OpenGate Logo">
  </a>
</p><br>

<p align="center">
  <a href="https://ozkantanrikulu.com" target="_blank" rel="noopener noreferrer"><img src="https://img.shields.io/badge/Powered%20by-OZKAN%20TANRIKULU-1e6eb5?style=plastic" alt="Powered by OZKAN TANRIKULU"></a>&nbsp;&nbsp;<a href="#"><img src="https://img.shields.io/badge/version-1.0.3-e94560?style=plastic" alt="Version"></a>&nbsp;&nbsp;<a href="#"><img src="https://img.shields.io/badge/macOS-14.0+-000000?style=plastic" alt="macOS"></a>&nbsp;&nbsp;<a href="#"><img src="https://img.shields.io/badge/Silicon%20%26%20Intel-compatible-cd7700?style=plastic" alt="Architecture"></a>&nbsp;&nbsp;<a href="#"><img src="https://img.shields.io/badge/license-Proprietary-9b59b6?style=plastic" alt="License"></a>&nbsp;&nbsp;<a href="https://virustotal.com/gui/file/48d0ed815c7a0c738ff047da4a81f33deb479abfd28516b7652a0f8746f6edbc" target="_blank" rel="noopener noreferrer"><img src="https://img.shields.io/badge/VirusTotal-Clean-brightgreen?style=plastic&logo=virustotal&logoColor=white" alt="VirusTotal"></a>
</p><br>


---

## What is OpenGate?

OpenGate is a native macOS application designed for DPI bypass and censorship circumvention. Built on a high-performance Go core, it effectively defeats ISP restrictions through advanced techniques such as SNI fragmentation, TCP segmentation, and DNS-over-HTTPS (DoH). By employing multi-layered packet-splitting strategies, it neutralizes Deep Packet Inspection (DPI) at the source. Featuring a minimalist, one-click interface, OpenGate offers a user-friendly experience that requires zero technical knowledge.

---

## Features

- **SNI Fragmentation** — Splits TLS Client Hello packets to prevent hostname-based filtering
- **TCP Segmentation** — Breaks TCP streams into small segments to confuse stateful DPI engines
- **DNS-over-HTTPS (DoH)** — Encrypts all DNS queries over HTTPS, eliminating DNS-based blocking and surveillance
- **Automatic System Proxy** — Instantly routes all macOS network traffic through the bypass core with a single click
- **Local Network Broadcasting** — Turns your Mac into a proxy server, extending DPI protection to every device on your local network
- **Launch at Login** — Automatically activates protection when you log in
- **Universal Binary** — Runs natively on both Apple Silicon and Intel Macs

---

## Performance

OpenGate is engineered and optimized for minimal resource consumption.

| Metric | Value |
|--------|-------|
| RAM Usage | ~20 MB (stable, background) |
| CPU Usage | <0,1% (idle) |
| Battery Impact | Negligible |
| Network Speed | No reduction |
| Initial Handshake Latency | + 30–150 ms |

> SNI fragmentation causes a brief delay of 30–150 ms only during each new connection handshake; once established all subsequent data flows at full speed without any performance loss.

---

## Installation

1. Download the latest `OpenGate.dmg` from [Releases](https://github.com/lastparody/opengate/releases)
2. Open the DMG and drag **OpenGate.app** to your Applications folder
3. On first launch, if macOS shows a security warning:
   - Close the dialog
   - Go to **System Settings → Privacy & Security**
   - Click **"Open Anyway"**

> OpenGate is not notarized by Apple. This is expected for open-distribution software. The security warning is a standard macOS Gatekeeper prompt.

---

## How to Use

1.  Download the latest `OpenGate.zip` from the [Releases](https://www.google.com/search?q=https://github.com/lastparody/opengate/releases) page.
2.  Extract the ZIP file and drag **OpenGate.app** into your **Applications** folder.
3.  When you first launch the app, macOS will display a security warning. To bypass this:
      - Click **"OK"** to close the dialog.
      - Go to **System Settings → Privacy & Security** on your Mac.
      - Scroll down and click the **"Open Anyway"** button.
      - Confirm by entering your password or using Touch ID, then click **"Open"**.

> OpenGate is not notarized by Apple. This is expected for independent, open-distribution software. The security warning is a standard macOS prompt and does not indicate any security risk.

---

## Settings

| Setting | Description |
|---------|-------------|
| Local Network Gateway | IP address for the bypass tunnel (default: 127.0.0.1) |
| DNS Address | DNS resolver address (default: 8.8.8.8) |
| Connection Port | Local port for the bypass core (default: 9090) |
| Secure DNS (DoH) | Encrypts DNS queries over HTTPS |
| IPv4 Priority | Forces DNS resolution to IPv4 for maximum stability |
| Network Scope | System-wide or application-based proxy mode |
| Proxy Broadcast | Share protection with other devices on your network |
| Launch at Startup | Auto-connect when you log in |

---

## FAQ

**❓ Does OpenGate slow down my internet?**
- No. It does not cause any bandwidth performance loss. Due to SNI fragmentation, a brief delay of 30–150 ms occurs only during each new connection handshake; once established, all subsequent data flows at full line speed.

**❓ Does it drain my battery?**
- No. The Go core is event-driven and sleeps when idle. CPU usage stays below **0.1%** during normal operation.

**❓ How much RAM does it use?**
- Approximately **20 MB**, stable. Does not grow over time.

**❓ Do I need to keep the app open?**
- Yes. Enable **Launch at Startup** in settings to start it automatically on login.

**❓ Can I use it on other devices on the same network?**
- Yes. Enable **Proxy Broadcast Station** in settings, then configure the target device manually.

**❓ Is my traffic logged?**
- No. OpenGate runs entirely on your device. No data is sent to any external server.
  
---

## License

This software is proprietary. See [LICENSE](https://github.com/lastparody/opengate/blob/main/LICENSE) for full terms.

---

<p align="center">
2026 <a href="https://ozkantanrikulu.com">Özkan Tanrıkulu</a>  © OpenGate All Rights Reserved
    <br><a href="mailto:ozkantanrikulu98@gmail.com">ozkantanrikulu98@gmail.com</a>
</p>
