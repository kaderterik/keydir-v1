# 📦 Kullanım Kılavuzu: keydır v1.0

> *"Sims kutusu" estetiğinde, Stardew Valley ruhlu, eğlenceli bir **interaktif kişisel tanıtım sitesi.***
> Bir insanı sanki kutulu bir ürünmüş gibi tanıtan; özellikleri, uyarıları, kullanım kılavuzu, arkadaş/aile modülleri, gardırop, uyumluluk testi, başarımlar ve yorumlarla donatılmış tek sayfalık (single‑page) bir web uygulaması.

Bu proje, **İnternet Programlama** dersi kapsamında geliştirilmiş kişisel bir "kendini tanıtma" web sitesidir. Kullanıcıyı (Kader / "keydır") kutulu bir elektronik ürün gibi sunan esprili bir konsept üzerine kuruludur: kişilik özellikleri "ürün özellikleri", anılar "koleksiyon", arkadaşlar/aile "destek modülleri", ilişki uyumu ise "uyumluluk testi" olarak sunulur.Ayrıca canlı ortamda erişebilmek için bu linke tıklayabilirsiniz: https://keydir-v1-internet.vercel.app/

---

## 🎮 Canlı Demo / Önizleme

Projeyi çalıştırmak için `index.html` dosyasını bir tarayıcıda açmanız yeterlidir (detaylar [Kurulum](#-kurulum--çalıştırma) bölümünde).

---

## ✨ Özellikler

Site, tek bir `index.html` içinde, kaydırmalı (scroll) bölümler halinde aşağıdaki modülleri barındırır:

| # | Bölüm | Açıklama |
|---|-------|----------|
| 1 | **Yükleme Ekranı** | "☕ Kahve yükleniyor...", "🧠 Düşünme modülü aktif..." gibi esprili mesajlarla açılış animasyonu |
| 2 | **Hero (Kapak)** | Ürün başlığı, alt başlık, pixel-art karakter sprite'ı |
| 3 | **Hotspot (Anatomi Şeması)** | Karaktere tıklanabilen 6 "donanım noktası" (Kafa/CPU, Güç Kaynağı, Sağ El, Sol El, Ayaklar, Alarm Sensörü) – her biri konuşma balonunda esprili açıklama gösterir |
| 4 | **Özellikler** | Kişilik etiketleri (chip'ler), kalp ikonlu performans istatistikleri (Sabah Performansı, Kafein Bağımlılığı vb.), kutu içeriği listesi |
| 5 | **Uyarılar** | Kırmızı/sarı renk kodlu "kullanım uyarıları" kartları (Sabah Protokolü, Yakıt Uyarısı, Gece Döngüsü, Sınav Haftası Hatası…) |
| 6 | **Rehber** | "Tanışma adımları" + Stardew Valley tarzı NPC diyalog kutusu ile **sevilen/sevilmeyen hediyeler** sistemi (hediyeye tıkla, tepkisini gör, "arkadaşlık puanı" anında değişsin) |
| 7 | **Koleksiyon (Akordeon)** | Açılır-kapanır sekmeler: 🎬 Filmler & Diziler, 🎵 Şarkılar (arka planda çalan mini müzik çalar), 👥 Arkadaşlar, 🏠 Aile, 🎓 Lise & Üniversite anıları — her kişi için galeri, fotoğraf lightbox'ı ve "yakınlık" göstergesi |
| 8 | **Kıyafet Odası** | Katmanlı (beden/saç/üst/alt/ayakkabı) sürükle-bırak tarzı **giydirme mini oyunu**, renk seçenekleri ve "rastgele kombin" butonu |
| 9 | **Uyumluluk Testi** | 3 adımlı (chip seçimi → evet/hayır soruları → sonuç) bir mini quiz; sonunda uyum skoru, progress bar, konfeti animasyonu ve "haftalık reaksiyon"  |
| 10 | **Başarımlar (Achievements)** | Gizli görevleri tamamlayınca (karanlık mod açma, karakter tıklama, gece ziyareti, gizli kod yazma vb.) açılan rozet/toast bildirim sistemi |
| 11 | **Yorumlar & Puanlama** | Ziyaretçilerin yıldızlı puan + yorum bırakabildiği, **Firebase Realtime Database** ile gerçek zamanlı senkronize olan yorum paneli (ortalama puan, dağılım çubukları, sıralama) |
| 12 | **Mevsim Widget'ı** | Güncel tarihe göre "Stardew Valley mevsimi" ve gün sayısını gösteren dekoratif takvim bileşeni |
| 13 | **QR Kod & Paylaşım** | `qrcode.js` ile sayfa linkini QR koda çeviren paylaşım modalı, `html2canvas` ile ekran görüntüsü/kart oluşturma altyapısı |
| 14 | **Tema Değiştirici** | Açık (Sage Green) / Koyu (Stardew gece) tema; `localStorage` ile tercih hatırlanır |
| 15 | **Ses Efektleri** | Tıklama, "blip", mutlu ses ve hata sesleri (Web Audio API ile, kod içinde sentezlenmiş) |
| 16 | **Gizli Easter Egg'ler** | Klavyeden gizli kelime yazma ("Konami kod" tarzı) ve mobilde **telefonu sallama** ile tetiklenen "bozulma/glitch" temalı sürpriz mod |
| 17 | **Parçacık (Particles) Arka Planı** | Canvas tabanlı, mevsime göre değişen yumuşak parçacık animasyonu |
| 18 | **Responsive Tasarım** | Mobil ve masaüstü için uyarlanmış, dokunmatik etkileşimlere göre optimize edilmiş arayüz |

---

## 🛠️ Kullanılan Teknolojiler

- **HTML5** – Tüm sayfa tek bir `index.html` dosyasında, semantik `<section>` yapılarıyla
- **CSS3** – CSS değişkenleri (`:root`) ile tema yönetimi, flexbox/grid tabanlı layout, animasyonlar
- **Vanilla JavaScript (ES6+)** – Harici framework kullanılmadan tüm interaktif mantık (DOM manipülasyonu, Web Audio API, Canvas API)
- **[Firebase Realtime Database](https://firebase.google.com/)** – Yorum/puanlama verilerinin gerçek zamanlı saklanması ve senkronizasyonu
- **[html2canvas](https://html2canvas.hertzen.com/)** – Sayfanın/kartların görsele dönüştürülmesi
- **[qrcode.js](https://davidshimjs.github.io/qrcodejs/)** – Paylaşım linki için QR kod üretimi
- **Google Fonts** – `Pixelify Sans` (piksel/retro his), `Nunito` (yumuşak gövde metni), `Caveat` (el yazısı notlar)

> Not: Proje herhangi bir build aracı (Webpack/Vite vb.) veya backend sunucusu gerektirmez; saf istemci taraflı (client-side) bir uygulamadır.

---

## 📁 Proje Yapısı

```
İnternet Programlama/
├── index.html              # Tüm HTML + CSS + JS bu dosyada (single-file app)
├── README.md                # Bu dosya
├── Müzikler/                 # Koleksiyon bölümünde çalınan mp3 dosyaları
│   ├── ebru.mp3
│   ├── eminem_without_me.mp3
│   ├── mehmet.mp3
│   ├── seksendort__aklimi_geri_ver_official_video_.mp3
│   ├── son_feci_bisiklet_torna.mp3
│   └── the_weeknd_reminder.mp3
└── gorseller/                # Tüm görseller, kategoriye göre alt klasörlerde
    ├── karakter1.png, karakter2.png, karakter_portre.png   # Ana karakter sprite'ları
    ├── kiyafetgiydirme/      # Gardırop katman görselleri (üst/kombin PNG'leri)
    ├── filmler/              # Film/dizi afişleri
    ├── müzik/                # Şarkı kapak görselleri
    ├── citir/, ebru/, mehmet/, kardesler/, lise/, univeriste/   # Arkadaş & aile galerileri
    └── keydir-Kullanim-Kilavuzu-Gorsel.pdf
```

---

## 🚀 Kurulum & Çalıştırma

Projenin herhangi bir derleme (build) adımına ihtiyacı yoktur.

### Yöntem 1 – Doğrudan açma
`index.html` dosyasına çift tıklayıp tarayıcıda açmanız yeterlidir.

> ⚠️ Bazı tarayıcılar `file://` protokolünde ses/medya dosyalarını veya bazı script özelliklerini kısıtlayabilir. En sağlıklı deneyim için bir yerel sunucu üzerinden çalıştırmanız önerilir.

### Yöntem 2 – Yerel sunucu ile (önerilen)
```bash
# Proje klasörüne girin
cd "İnternet Programlama"

# Python varsa:
python3 -m http.server 8000

# veya Node.js varsa:
npx serve .
```
Ardından tarayıcıdan `http://localhost:8000` adresine gidin.

### Yöntem 3 – VS Code Live Server
VS Code'da "Live Server" eklentisini kurup `index.html` üzerinde sağ tıklayıp **"Open with Live Server"** seçeneğini kullanabilirsiniz.

---

## ⚙️ Özelleştirme (Kendi Bilgilerinizle Doldurma)

Sitedeki **tüm içerik** `index.html` içindeki tek bir `CONFIG` JavaScript objesinden (`<script>` bölümü, "BÖLÜM 1: CONFIG OBJESİ" yorumundan itibaren) yönetilir. Yeni bir kişi/proje için uyarlamak isterseniz şu alanları düzenlemeniz yeterlidir:

- `CONFIG.isim`, `CONFIG.versiyon`, `CONFIG.sosyalMedya` → kimlik & sosyal medya linkleri
- `CONFIG.hotspots` → karakter üzerindeki tıklanabilir noktalar ve açıklamaları
- `CONFIG.ozellikler`, `CONFIG.istatistikler`, `CONFIG.kutuIcerigi` → kişilik kartları
- `CONFIG.uyarilar` → uyarı kartları
- `CONFIG.rehber` → tanışma adımları + sevilen/sevilmeyen "hediyeler"
- `CONFIG.koleksiyon` → filmler, şarkılar, arkadaşlar, aile kartları (fotoğraf yolları dahil)
- Gardırop katmanları → "BÖLÜM 7: KIYAFET ODASI" yorumunun altında
- Uyumluluk testi soruları → "BÖLÜM 8: UYUMLULUK TESTİ CONFIG" yorumunun altında
- `ACHIEVEMENTS` dizisi → başarım/rozet tanımları (sayfanın daha aşağısındaki ayrı `<script>` bloğunda)

---

## 🔥 Firebase Yapılandırması Hakkında Not

Yorumlar bölümü, verileri bir **Firebase Realtime Database** projesine yazıp okuyor. Yapılandırma bilgileri (`firebaseConfig`) doğrudan `index.html` içinde tanımlı durumda. Bu, Firebase'in istemci taraflı projelerde **normal ve beklenen** bir kullanım şeklidir (bu anahtarlar gizli/sır niteliğinde değildir) — ancak veritabanınızı kötüye kullanıma karşı korumak için Firebase konsolunda **Realtime Database Security Rules** (okuma/yazma izinleri, hız sınırlama vb.) tanımlamanız şiddetle önerilir.

Kendi kopyanızı çalıştırmak isterseniz:
1. [Firebase Console](https://console.firebase.google.com/) üzerinden yeni bir proje oluşturun.
2. Realtime Database'i etkinleştirin.
3. `index.html` içindeki `firebaseConfig` objesini kendi proje bilgilerinizle değiştirin.

---

## 🥚 Gizli Özellikler (Easter Egg)

- **Gizli kelime:** Sayfa açıkken klavyeden ilgili gizli kelimeyi yazmayı deneyin → "bozulma/glitch" temalı özel bir mod tetiklenir. 🎮
- **Telefonu sallama:** Mobil cihazda sayfayı ziyaret edip telefonu salladığınızda da aynı sürpriz mod devreye girer. 📳
- **Başarımlar:** Karanlık modu açmak, karaktere art arda tıklamak, gece saatlerinde siteyi ziyaret etmek, 10 fotoğraf açmak gibi gizli görevler rozet kazandırır — sağ üstteki başarımlar simgesinden ilerlemenizi takip edebilirsiniz.

---

## 👩‍💻 Hakkında

**Geliştiren:** Kader Terik — Bilgisayar Mühendisliği Öğrencisi, Balıkesir Üniversitesi (BAUN)

- 🔗 GitHub: [github.com/kaderterik](https://github.com/kaderterik)
- 💼 LinkedIn: [linkedin.com/in/kaderterik](https://www.linkedin.com/in/kaderterik)
- 📸 Instagram: [@kadrtrkk](https://www.instagram.com/kadrtrkk/)

---

## 📄 Lisans

Bu proje bir **İnternet Programlama** ders ödevi/projesi olarak hazırlanmıştır ve kişisel içerik (fotoğraf, isim, anı vb.) barındırmaktadır. Kod yapısı eğitim/referans amaçlı incelenebilir; içerikteki kişisel görsel ve metinlerin izinsiz kopyalanması/yeniden yayınlanması uygun değildir.

> *"Bu ürünün izinsiz kopyalanması yasaktır."*
