<div align="center">

# 🔐 Lenze PLC Key Generator

**Lenze PLC uygulamaları için makine kimliğine bağlı lisans anahtarı üretim aracı**

[![Son Sürüm](https://img.shields.io/github/v/release/isa-ozturk/LenzePLCKeyGenerator-releases?label=son%20s%C3%BCr%C3%BCm&color=2196F3)](https://github.com/isa-ozturk/LenzePLCKeyGenerator-releases/releases/latest)
[![İndirme](https://img.shields.io/github/downloads/isa-ozturk/LenzePLCKeyGenerator-releases/total?label=indirme&color=0F7B0F)](https://github.com/isa-ozturk/LenzePLCKeyGenerator-releases/releases)
![Platform](https://img.shields.io/badge/platform-Windows%2010%20%7C%2011-0078D4)
![.NET Framework](https://img.shields.io/badge/.NET%20Framework-4.7.2-512BD4)

[**⬇️ Son Sürümü İndir**](https://github.com/isa-ozturk/LenzePLCKeyGenerator-releases/releases/latest) ·
[Sürüm Notları](https://github.com/isa-ozturk/LenzePLCKeyGenerator-releases/releases) ·
[Hata Bildir](https://github.com/isa-ozturk/LenzePLCKeyGenerator-releases/issues/new/choose)

</div>

---

## Hakkında

**Key Generator**, Lenze Türkiye bünyesinde geliştirilen PLC uygulamalarında kullanılan süreli ve süresiz lisansların yönetimi için hazırladığım bir masaüstü aracıdır. Cihaz ekranında görüntülenen **Makine ID** ve cihaza tanımlı **Müşteri Kodu** ile, yalnızca o cihazda geçerli olan lisans anahtarını saniyeler içinde üretir.

Bu depo, uygulamanın **derlenmiş sürümlerinin, sürüm notlarının ve hata kayıtlarının** resmi yayın noktasıdır. Uygulama içindeki otomatik güncelleme mekanizması da yeni sürümleri doğrudan bu depodan alır.

> [!NOTE]
> Uygulamanın kaynak kodu kurum içinde ayrı ve kapalı bir depoda geliştirilmektedir. Bu depoda yalnızca son kullanıcıya yönelik dağıtım dosyaları yer alır.

---

## Öne Çıkan Özellikler

| | Özellik | Açıklama |
|---|---|---|
| 🔑 | **Makine ID tabanlı lisans** | Her anahtar yalnızca ait olduğu cihazın seri numarası ve çalışma günü ile eşleşir. |
| 🏢 | **Müşteri kodu doğrulaması** | Makine ID içine gömülü müşteri kodu, girilen kod ile birebir eşleşmeden anahtar üretilmez. |
| 🛡️ | **Bütünlük kontrolü** | Hatalı yazılmış veya değiştirilmiş makine ID'leri imza doğrulaması ile reddedilir. |
| 📅 | **Esnek lisans türleri** | Ay bazlı (1–12 ay), gün bazlı (1–30 gün) ve limitsiz lisans. |
| 🔄 | **Otomatik güncelleme** | Yeni sürümler açılışta kontrol edilir; sürüm notlarıyla birlikte tek tıkla kurulur. |
| 📦 | **Tek dosya** | Kurulum gerektirmez; tek bir `KeyGenerator.exe` ile çalışır. |

---

## Sistem Gereksinimleri

| Bileşen | Gereksinim |
|---|---|
| İşletim Sistemi | Windows 10 (1809 ve üzeri) veya Windows 11 |
| Çalışma Ortamı | .NET Framework 4.7.2 veya üzeri *(Windows 10/11 ile birlikte gelir)* |
| Ağ | Yalnızca güncelleme kontrolü için `github.com` erişimi *(anahtar üretimi çevrimdışı çalışır)* |
| Yetki | Yönetici yetkisi gerekmez |

---

## Kurulum

1. [Releases](https://github.com/isa-ozturk/LenzePLCKeyGenerator-releases/releases/latest) sayfasından en güncel `KeyGenerator.exe` dosyasını indirin.
2. Dosyayı kalıcı olarak kullanacağınız bir klasöre taşıyın *(ör. `C:\Tools\KeyGenerator\`)*.
3. Çift tıklayarak çalıştırın.

> [!TIP]
> İlk çalıştırmada Windows SmartScreen uyarısı görüntülenebilir. **Ek bilgi → Yine de çalıştır** seçeneği ile devam edebilirsiniz. Dosyanın bütünlüğünü, her sürüm notunun altında yayınlanan **SHA-256** değeri ile doğrulayabilirsiniz:
>
> ```powershell
> Get-FileHash .\KeyGenerator.exe -Algorithm SHA256
> ```

---

## Kullanım

1. **Makine ID** — Cihaz ekranındaki `XXXX-XXXX-XXXX` formatındaki kodu girin. Tireler otomatik eklenir, küçük harfler büyük harfe çevrilir.
2. **Müşteri Kodu** — Cihaza tanımlı müşteri kodunu girin *(ör. `7`, `T01`, `A123`, `TX01`)*. Cihazda müşteri kodu tanımlı değilse alanı boş bırakın.
   > Kodlar **birebir** karşılaştırılır: `T01`, `T1` ve `T001` farklı kodlardır.
3. **Lisans Türü ve Süresi** — Ay bazlı, gün bazlı veya limitsiz seçeneğini ve süreyi belirleyin.
4. **Anahtar Oluştur** — Üretilen anahtarı kopyalama butonu ile panoya alın ve cihaza girin.

### Olası Uyarılar

| Mesaj | Anlamı |
|---|---|
| *Geçersiz format* | Makine ID 12 haneli (`XXXX-XXXX-XXXX`) değil. |
| *Makine ID doğrulanamadı* | Kod eksik veya hatalı yazılmış; cihaz ekranındaki kodu tekrar kontrol edin. |
| *Bu makine kimliği belirtilen müşteri koduna ait değildir* | Girilen müşteri kodu, cihaza tanımlı kod ile eşleşmiyor. Bu cihaz için anahtar üretilemez. |

---

## Güncellemeler ve Eski Sürümler

- Uygulama her açılışta bu depodaki son sürümü kontrol eder. Yeni bir sürüm varsa, aradaki tüm sürümlerin notları ile birlikte bir güncelleme penceresi açılır.
- Güncelleme durumunu sol alt köşedeki sürüm bilgisine tıklayarak elle de kontrol edebilirsiniz.
- Tüm sürümlere ve sürüm notlarına [Releases](https://github.com/isa-ozturk/LenzePLCKeyGenerator-releases/releases) sayfasından ulaşabilirsiniz. Önceki bir sürüme ihtiyaç duyarsanız ilgili sürümün **Assets** bölümünden indirebilirsiniz.

> [!IMPORTANT]
> **v2.0.0** ile birlikte yeni nesil (v4) makine kimliği yapısına geçilmiştir. Bu sürüm ve sonrası yalnızca `XXXX-XXXX-XXXX` formatındaki makine ID'lerini destekler.

---

## Hata Bildirimi ve Öneriler

Karşılaştığınız sorunları veya geliştirme önerilerinizi [Issues](https://github.com/isa-ozturk/LenzePLCKeyGenerator-releases/issues/new/choose) bölümünden iletebilirsiniz. Bildiriminizde şunları belirtmeniz süreci hızlandırır:

- Uygulama sürümü *(sol alt köşede yazar)* ve Windows sürümü
- Sorunun adım adım nasıl oluştuğu ve ekran görüntüsü

> [!CAUTION]
> Bu depo herkese açıktır. Bildirimlerinizde **lisans anahtarı, müşteri kodu, makine ID veya cihaz seri numarası paylaşmayın.** Bu bilgiler gerekiyorsa sizinle ayrıca iletişime geçilecektir.

---

## Geliştirici

**İsa Öztürk** — Lenze Türkiye IT

---

<div align="center">

© 2025–2026 Lenze Türkiye. Tüm hakları saklıdır.<br/>
<sub>Bu yazılım Lenze Türkiye ve yetkilendirilmiş iş ortaklarının kullanımı içindir. İzinsiz çoğaltılması ve dağıtılması yasaktır.</sub>

</div>
