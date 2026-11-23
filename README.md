# LOAGEN bio sayfası

Instagram'daki link-in-bio sayfamız. Yayında: **https://bio.loagen.com.tr**

Bu repo sayfanın **tek ve güncel kaynağıdır**. Düzenleme gerekirse buradan yapılır; başka yerde kopya tutulmaz.

## Yayın nasıl çalışıyor

- GitHub Pages, `main` dalının kökünden yayınlar. `main`'e push edildikten 1–2 dakika sonra site güncellenir.
- Alan adı: `CNAME` dosyasında `bio.loagen.com.tr`. DNS kaydı hosting.com.tr panelinde: CNAME `bio` → `harryhourson.github.io`. HTTPS açık.
- `.nojekyll` dosyası silinmez (Pages dosyaları olduğu gibi sunsun diye).
- `CNAME` dosyası silinmez; silinirse alan adı düşer.

## Dosyalar

| Dosya | Ne |
|---|---|
| `index.html` | Bütün sayfa: HTML, CSS, JS tek dosyada (dış bağımlılık yalnızca Google Fonts, Montserrat 500/600/700). |
| `icerik.json` | Video şeridi ve blog kartı. Yeni video/blog eklemek için yalnızca bunu düzenlemek yeter. |
| `img/logo.png`, `img/logo-merkez.png` | Logo (şeffaf). Üstteki krem rozette `logo-merkez.png` kullanılır (optik ortalanmış). |
| `img/magnativ-kesim.png`, `img/folinativ-kesim.png` | Ürün kartlarındaki 3B kutu görselleri (şeffaf). `magnativ.jpg`/`folinativ.jpg` yedek. |
| `img/podcast-kapak.jpg` | Podcast kapağı (800×800). Kapak değişirse yeni dosya adı ver ve `index.html`'deki 6 referansı güncelle (önbellek yüzünden aynı adla değiştirme). |
| `img/yumurta.jpg`, `yuru.jpg`, `adim.jpg` | Video kapakları. |
| `img/blog.jpg` | Blog kartı görseli. |

## Sayfanın bölümleri (yukarıdan aşağı)

1. **Üst kısım:** krem rozette logo, "LOAGEN", slogan, arka planda nokta alanı (parıltılı yıldızlar), blur reveal girişler.
2. **Ürünler:** Magnativ ve Folinativ kartları. Altında **loagen.com.tr / Trendyol** anahtarı; seçime göre kart linkleri değişir (`data-site` / `data-ty`).
   - Magnativ: site `https://www.loagen.com.tr/products/magnativ-magnezyum?utm_source=link&utm_medium=bio&utm_campaign=magnativ`, Trendyol `https://ty.gl/iy0losyx2j37b`
   - Folinativ: site `https://www.loagen.com.tr/products/folinativ-folik-asit?utm_source=link&utm_medium=bio&utm_campaign=folinativ`, Trendyol `https://ty.gl/0g663m89gvj3a`
   - Ürünün adı **Magnativ** (Magmativ değil).
3. **Uygulama kartı** (`section.app`, `#appc`): gebelik ve çocuk takibi uygulaması. Kartta marka adı yazılmaz (kullanıcı: sayfada zaten çok "LOAGEN" var); başlık "Gebelik ve çocuk takibi". 3B: kart parmak/fareyle eğilir, boştayken yavaşça salınır; sağda CSS ile çizilmiş telefon (24. hafta halkası, hatırlatıcı, rehber, çubuklar) ve önünde iki yüzen etiket ("Vitamin vakti", "Bebek ~600 g"). Telefon ekranındaki içerik temsilidir, uygulamanın gerçek ekranı değildir. Google Play linki `https://play.google.com/store/apps/details?id=app.web.loagenapp.twa`. App Store şimdilik "Yakında" (tıklanamaz `div.st.soon`); yayına girince `<a class="st" href="...">` yapılıp üstteki küçük yazı "ŞİMDİ İNDİR" olacak.
4. **Podcast destesi:** üst üste üç kart (Spotify, Apple Podcasts, Hakkında). Hakkında kartında açıklama Star Wars kayan yazısı gibi akar (36 sn, vurgular krem). Altta Spotify / Apple / Hakkında sekmeleri.
   - Spotify ve Apple linkleri şimdilik arama sayfası (`open.spotify.com/search/Loagen`, `podcasts.apple.com/search?term=Loagen`). **Show yayına girince gerçek linklerle değiştirilecek.**
5. **Videolar:** coverflow şeridi, kendi kendine kayar; içerik `icerik.json` → `videolar`. Platform kodları: `YT`, `IG`, `TT`.
6. **Blog kartı:** `icerik.json` → `blog`.
7. **Sosyal ikonlar:** Instagram, TikTok, YouTube (`@loagenturkiye`).

## Marka kuralları

- Yazı tipi yalnızca **Montserrat** (500/600/700).
- Renkler (`:root` içinde): lacivert `#23406A`, koyu `#1b3358`, adaçayı `#ACB187`, krem `#F4ECA3`, yazı `#F7F3D6`. Palet dışı renk eklenmez (Spotify yeşili ve Apple moru yalnızca kendi butonlarında).
- Fotoğraflar doğal renginde kalır; üstüne lacivert filtre konmaz.
- Sayfa telefon için tasarlandı (375 px genişlikte kontrol et). Masaüstünde ortada dar sütun.

## Düzenleme sonrası kontrol

1. Yerelde aç: klasörde `python -m http.server 8000` → `http://localhost:8000` (telefon genişliğinde bak).
2. `main`'e push et.
3. 1–2 dk sonra `https://bio.loagen.com.tr/?v=<rastgele>` ile kontrol et (önbelleği atlatmak için).

## Yapılacaklar

- Podcast Spotify/Apple linkleri yayına girince güncellenecek.
- Uygulamanın App Store linki gelince kart güncellenecek.
- Kullanıcının istediği, ileride: sayfayı düzenlemek için basit bir kontrol paneli (video/blog/ürün ekle-çıkar, `icerik.json`'u besleyecek).
- `loagen.com.tr` alan adı 15.12.2026'da bitiyor; otomatik yenileme pasifti. Biterse `bio.` alt alan adı da düşer.
