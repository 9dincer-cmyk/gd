---
name: meta-ads-strategy
description: Planning and optimizing Meta (Facebook/Instagram) ads for Cabani — account structure (Advantage+ Shopping, catalog/DPA retargeting, prospecting), audiences, creative and copy recommendations, budget, Pixel/Conversions API checks. Use when the user asks for Meta reklam önerisi, Facebook/Instagram reklam kurgusu, reklam görseli/metni fikri, or why Meta ads aren't selling.
---

# Meta reklam stratejisi

Performans verisi analizi için `ads-performance-review`, rakip reklamları için
`competitor-analysis` (AdWhispr) kullan. Bu skill **kurgu ve öneri** içindir.
**Kampanya oluşturma, yayına alma, bütçe değiştirme kullanıcı onayı olmadan yapılmaz.**

## 1. Ön koşul kontrolü (öneriden önce)
- **Pixel + Conversions API** kurulu mu, `ViewContent`, `AddToCart`,
  `InitiateCheckout`, `Purchase` olayları değerle (TRY) gidiyor mu?
  Ticimax'ta Meta Pixel/CAPI entegrasyonu panelden yapılır. Canlı sayfada
  `fbq(` / `connect.facebook.net` arayarak pixel varlığını doğrula.
- **Katalog:** Ticimax ürün XML/feed'i Commerce Manager'a bağlı mı; ürün
  ID'leri pixel olaylarındaki `content_ids` ile eşleşiyor mu (DPA için şart).
- Alan adı doğrulama ve toplu olay ölçümü.

## 2. Önerilen hesap yapısı (küçük-orta bütçe)
| Katman | Kampanya | Bütçe payı |
|---|---|---|
| Soğuk kitle | **Advantage+ Shopping** (ASC) — geniş hedefleme, katalog + en iyi 3-6 kreatif | %60-70 |
| Soğuk (test) | Kreatif test kampanyası, ABO, reklam seti başına tek kreatif konsepti | %10-15 |
| Sıcak kitle | **Katalog retargeting (DPA)** — son 7-14 gün ürün görüntüleyen/sepete ekleyen, satın alanlar hariç | %15-25 |
Az kampanya, az reklam seti: öğrenme aşamasından çıkmak için reklam seti
başına haftada ~50 dönüşüm hedeflenir; veri azsa yapıyı daha da sadeleştir.

## 3. Kreatif önerileri (en büyük kaldıraç)
- Formatlar: 9:16 Reels/Story (ilk 2 saniyede ürün + kanca), 1:1/4:5 carousel
  (koleksiyon), katalog reklamında fiyat/indirim etiketli çerçeve.
- Açılar: fayda, sosyal kanıt (müşteri yorumu/UGC), kombin/kullanım, kampanya
  aciliyeti, "neden Cabani" (kargo, iade, kalite).
- Her konsept için 3 birincil metin + 3 başlık üret (`product-content-tr`
  kurallarıyla). Görseller için Canva bağlıysa taslak oluştur.
- Yorgunluk: frekans > 3 ve CTR düşüyorsa kreatifi yenile (2-3 haftada bir yeni konsept).

## 4. Metrik hedefleri (başlangıç kıyası, kendi verisiyle güncelle)
CTR (link) ≥ %1, CPM trendi, AddToCart oranı, CPA ≤ hedef, ROAS ≥ başabaş (1/marj).

## Çıktı
Hesap yapısı tablosu + bütçe dağılımı + 3 kreatif konsepti (metinleriyle) +
ön koşul kontrol listesi (✅/❌) + ilk 14 günlük test planı.
