---
name: ecommerce-seo-audit
description: SEO audit checklist for the Cabani e-commerce site (www.cabani.com.tr, Ticimax) — technical SEO, category/product page on-page SEO, schema.org Product/Breadcrumb markup, and Turkish keyword targeting. Use when the user asks for an SEO denetimi, "neden Google'da çıkmıyoruz", meta/title/schema review, or sitemap/robots/indexing checks.
---

# E-ticaret SEO denetimi (Cabani / Ticimax)

Panel erişimi gerektirmez; canlı URL'ler üzerinden yapılır (WebFetch / curl).
Bulguları her zaman **"Ticimax panelinden düzeltilebilir"** vs. **"tema kodu
gerektirir"** diye ayır — kullanıcının neyi hemen yapabileceği net olsun.

## 1. Teknik temel
- `https://www.cabani.com.tr/robots.txt` — sitemap satırı var mı, önemli
  dizinler (kategori, ürün) yanlışlıkla engellenmiş mi, filtre/sıralama
  parametreleri (`?sira=`, `?filtre=` vb.) crawl bütçesini yiyor mu.
- `sitemap.xml` — erişilebilir mi, ürün/kategori URL'leri var mı, 404/301
  dönen URL içeriyor mu (örnekle 20-30 URL'yi kontrol et).
- HTTP → HTTPS ve `cabani.com.tr` → `www` yönlendirmeleri tek adımlı 301 mi.
- Canonical: filtreli/sayfalı kategori URL'leri ana kategoriye mi işaret
  ediyor; ürün varyant URL'leri tek canonical'a mı bağlı.
- `hreflang` / `lang="tr"` doğru mu.

## 2. Sayfa şablonları (her şablondan 2-3 örnek sayfa)
Ana sayfa, kategori, ürün, blog/içerik sayfası için:
- `<title>` 50-60 karakter, benzersiz, ana anahtar kelime başta + marka sonda.
- Meta description 140-160 karakter, fayda + CTA (ücretsiz kargo, taksit vb.).
- Tek `<h1>`; kategori sayfasında H1 = kategori adı + niteleyici.
- Kategori sayfalarında ürün ızgarasının altında/üstünde 150-300 kelimelik
  özgün açıklama metni (Ticimax: Kategori → Açıklama alanı).
- Ürün sayfası: özgün açıklama (üretici metninin kopyası değil), görsel
  `alt` metinleri, iç linkler (ilgili ürünler, kategori breadcrumb).

## 3. Yapılandırılmış veri
- Ürün sayfasında `Product` + `Offer` (price, priceCurrency=TRY,
  availability) + varsa `AggregateRating`.
- `BreadcrumbList`, ana sayfada `Organization` + `WebSite` (SearchAction).
- Eksik/hatalı JSON-LD genelde tema kodu gerektirir → bunu açıkça belirt.

## 4. Performans & mobil
- Core Web Vitals (LCP, CLS, INP) — PageSpeed Insights API:
  `https://www.googleapis.com/pagespeedonline/v5/runPagespeed?url=...&strategy=mobile`
- Sık bulgular: sıkıştırılmamış banner görselleri, üçüncü parti betikler
  (chat, pixel'ler), lazy-load olmayan ürün görselleri.

## Çıktı formatı
Öncelik tablosu: **Bulgu | Etki (Yüksek/Orta/Düşük) | Efor | Nerede
düzeltilir (Panel / Tema kodu / İçerik)**. En yüksek etki × en düşük efor
en üstte. Tahmini değil, gözlenen kanıtı (URL + görülen değer) yaz.
