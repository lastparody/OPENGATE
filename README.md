<br>
<div id="türkçe"></div>

<p align="center">
  <a href="#_">
    <img src="https://raw.githubusercontent.com/lastparody/OPENGATE/main/.github/images/logo.svg" width="320" alt="OpenGate Logo">
  </a>
</p><br>

<p align="center">
  <a href="https://ozkantanrikulu.com" target="_blank" rel="noopener noreferrer"><img src="https://img.shields.io/badge/Powered%20by-ÖZKAN%20TANRIKULU-7c3aed?style=plastic" alt="Powered by ÖZKAN TANRIKULU"></a>&nbsp;&nbsp;<a href="#"><img src="https://img.shields.io/badge/version-1.0.5-e94560?style=plastic" alt="Version"></a>&nbsp;&nbsp;<a href="#"><img src="https://img.shields.io/badge/Windows-10%2F11-0078d7?style=plastic&logo=windows" alt="Windows"></a>&nbsp;&nbsp;<a href="#"><img src="https://img.shields.io/badge/macOS-14.0+-000000?style=plastic&logo=apple&logoColor=white" alt="macOS"></a>&nbsp;&nbsp;<a href="#"><img src="https://img.shields.io/badge/license-Proprietary-9b59b6?style=plastic" alt="License"></a>&nbsp;&nbsp;
</p> <br>


---

## OpenGate Nedir?

OpenGate, DPI bypass ve sansür atlatma için multi platform (Windows, macOS, Docker) destekli bir uygulamadır. Yüksek performanslı Go çekirdeği üzerine inşa edilmiştir. SNI parçalaması, TCP segmentasyonu ve DNS-over-HTTPS aracılığıyla internet servis sağlayıcılarının kısıtlamalarını atlatır. Çok katmanlı paket bölme teknikleriyle derin paket incelemeyi (DPI) devre dışı bırakır. Tek butonla çalışan sade bir arayüz, teknik bilgi gerektirmeyen kullanıcı dostu yapı.

---

## Özellikler

- **SNI Parçalama** — Ana makine adı tabanlı filtrelemeyi önlemek için TLS Client Hello paketlerini böler.
- **TCP Segmentasyon** — Durum bilgisi olan DPI motorlarının kafasını karıştırmak için TCP akışlarını küçük segmentlere ayırır.
- **DNS-over-HTTPS (DoH)** — Tüm DNS sorgularını HTTPS üzerinden şifreleyerek DNS tabanlı engellemeleri ve gözetimi ortadan kaldırır.
- **Otomatik Sistem Proxy** — Tek bir tıklamayla tüm sistem ağ trafiğini bypass çekirdeği üzerinden yönlendirir.
- **Yerel Ağ Yayın** — Cihazınızı bir proxy sunucusuna dönüştürerek DPI korumasını yerel ağınızdaki her cihaza genişletir.
- **Girişte Başlat** — Oturum açtığınızda korumayı otomatik olarak etkinleştirir.
- **Çoklu Platform** — Windows, Apple Silicon ve Apple Intel cihazlarda native çalışır.

---

## Performans

OpenGate düşük kaynak tüketimiyle çalışacak şekilde tasarlanmış ve optimize edilmiştir.

| Metrik | Değer |
|--------|-------|
| CPU Kullanımı | <%0,1 |
| Pil Etkisi | Minimal |
| Ağ Performansı  | Bant genişliği korunur |
| İlk Bağlantı Gecikmesi | + 30–150 ms |

> SNI parçalaması, yalnızca her yeni bağlantı kurulumundaki el sıkışma aşamasında 30–150 ms'lik bir gecikmeye neden olur; bağlantı sağlandıktan sonraki tüm veri akışı herhangi bir performans kaybı olmaksızın tam hızda gerçekleşir.

---

## Kurulum

### macOS
OpenGate, Apple tarafından güvenlik taramalarından geçirilmiş ve onaylanmış **Notarized** güvenilir bir yazılımdır.

1. En güncel macOS sürümünü **Releases** sayfasından indirin.
2. İndirdiğiniz **.dmg** dosyasına çift tıklayarak açın.
3. Açılan penceredeki **OpenGate** ikonunu, Uygulamalar klasörüne sürükleyip bırakın.
4. Uygulamalar klasöründen OpenGate'i çalıştırın ve kullanmaya başlayın!

### Windows (Portable)
1.  En güncel Windows sürümünü [Releases](https://github.com/lastparody/opengate/releases) sayfasından indirin.
2.  ZIP dosyasını açıp içindeki klasörü bilgisayarınızda `Program Dosyaları (x86)` gibi uygun bir konuma taşıyın (Kurulum gerektirmez).
3.  Klasör içerisindeki uygulama dosyasına sağ tıklayıp masaüstünüze bir kısayol oluşturarak kullanmaya başlayabilirsiniz.

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
- Hayır. Go çekirdeği olay odaklıdır ve boşta olduğunda uyku moduna geçer. Normal çalışma sırasında CPU kullanımı **%0.01**'in altında kalır.

**❓ Uygulamayı açık tutmam gerekiyor mu?**
- Evet. Oturum açıldığında otomatik olarak başlatmak için ayarlardan **Başlangıçta Çalıştır** seçeneğini etkinleştirin.

**❓ Aynı ağdaki diğer cihazlarda kullanabilir miyim?**
- Evet. Ayarlardan **Proxy Yayını** seçeneğini etkinleştirin, ardından hedef cihazı manuel olarak yapılandırın.

**❓ Trafiğim kayıt altına alınıyor mu ?**
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
  <a href="https://ozkantanrikulu.com" target="_blank" rel="noopener noreferrer"><img src="https://img.shields.io/badge/Powered%20by-OZKAN%20TANRIKULU-1e6eb5?style=plastic" alt="Powered by OZKAN TANRIKULU"></a>&nbsp;&nbsp;<a href="#"><img src="https://img.shields.io/badge/version-1.0.5-e94560?style=plastic" alt="Version"></a>&nbsp;&nbsp;<a href="#"><img src="https://img.shields.io/badge/Windows-10%2F11-0078d7?style=plastic&logo=windows" alt="Windows"></a>&nbsp;&nbsp;<a href="#"><img src="https://img.shields.io/badge/macOS-14.0+-000000?style=plastic&logo=apple&logoColor=white" alt="macOS"></a>&nbsp;&nbsp;<a href="#"><img src="https://img.shields.io/badge/license-Proprietary-9b59b6?style=plastic" alt="License"></a>&nbsp;&nbsp;
</p><br>


---

## What is OpenGate?

OpenGate is a native multi-platform (Windows, macOS) application designed for DPI bypass and censorship circumvention. Built on a high-performance Go core, it effectively defeats ISP restrictions through advanced techniques such as SNI fragmentation, TCP segmentation, and DNS-over-HTTPS (DoH). By employing multi-layered packet-splitting strategies, it neutralizes Deep Packet Inspection (DPI) at the source. Featuring a minimalist, one-click interface, OpenGate offers a user-friendly experience that requires zero technical knowledge.

---

## Features

- **SNI Fragmentation** — Splits TLS Client Hello packets to prevent hostname-based filtering
- **TCP Segmentation** — Breaks TCP streams into small segments to confuse stateful DPI engines
- **DNS-over-HTTPS (DoH)** — Encrypts all DNS queries over HTTPS, eliminating DNS-based blocking and surveillance
- **Automatic System Proxy** — Instantly routes all system network traffic through the bypass core with a single click
- **Local Network Broadcasting** — Turns your device into a proxy server, extending DPI protection to every device on your local network
- **Launch at Login** — Automatically activates protection when you log in
- **Multi-Platform** — Runs natively on Windows, Apple Silicon, and Apple Intel devices

---

## Performance

OpenGate is engineered and optimized for minimal resource consumption.

| Metric | Value |
|--------|-------|
| CPU Usage | <0,1% (idle) |
| Battery Impact | Negligible |
| Network Speed | No reduction |
| Initial Handshake Latency | + 30–150 ms |

> SNI fragmentation causes a brief delay of 30–150 ms only during each new connection handshake; once established all subsequent data flows at full speed without any performance loss.

---

## Installation

### macOS
1.  Download the latest macOS release from the [Releases](https://github.com/lastparody/opengate/releases) page.
2.  Extract the ZIP file and drag **OpenGate.app** into your **Applications** folder.
3.  When you first launch the app, macOS will display a security warning. To bypass this:
      - Click **"OK"** to close the dialog.
      - Go to **System Settings → Privacy & Security** on your Mac.
      - Scroll down and click the **"Open Anyway"** button.
      - Confirm by entering your password or using Touch ID, then click **"Open"**.

> OpenGate is not notarized by Apple. This is expected for open-distribution software. The security warning is a standard macOS Gatekeeper prompt.

### Windows (Portable)
1.  Download the latest Windows release from the [Releases](https://github.com/lastparody/opengate/releases) page.
2.  Extract the ZIP file and move the folder to a location like `C:\Program Files (x86)`. (It is a portable distribution and requires no installation).
3.  Right-click on the application executable inside the folder and create a shortcut on your desktop for easy access.

---

## How to Use

1. Launch OpenGate from the Applications folder.
2. Click the shield icon to establish the connection.
3. The icon will turn green once protection is activated.
4. All your internet traffic is now being routed through OpenGate.

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
- No. The Go core is event-driven and sleeps when idle. CPU usage stays below **0.01%** during normal operation.

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
