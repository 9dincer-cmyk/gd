---
name: cro-audit
description: Conversion-rate optimization (CRO) review for the Cabani online store — home, category, product, cart and checkout funnel, trust signals, mobile UX, and A/B test ideas. Use when the user wants to "satışları artır", improve dönüşüm oranı, reduce sepet terk, or review a page's UX for conversions.
---

# Dönüşüm oranı optimizasyonu (CRO) denetimi

Amaç: ziyaretçiyi alıcıya çeviren adımlardaki sürtünmeyi bulmak. Canlı siteyi
**mobil öncelikli** incele (Türkiye e-ticaret trafiğinin büyük kısmı mobil).
Mümkünse Playwright ile 390px genişlikte ekran görüntüsü al.

## Huni adımları ve kontrol listesi
**Ana sayfa:** 5 saniyede "ne satıyor, neden buradan almalıyım" anlaşılıyor mu;
hero banner'da net teklif + CTA; kategori erişimi 1 dokunuş.

**Kategori sayfası:** filtreler (beden, renk, fiyat) mobilde kullanışlı mı;
sıralama; ürün kartında fiyat, indirim oranı, stok/kargo rozeti; sonsuz
kaydırma vs sayfalama.

**Ürün sayfası:** ekranın üst yarısında fiyat + sepete ekle; çoklu, zoom'lu
görsel ve varsa video; beden tablosu; kargo süresi + ücretsiz kargo eşiği;
iade koşulu; taksit seçenekleri; yorumlar/puan; stok aciliyeti (dürüst olmak
şartıyla); çapraz satış.

**Sepet & ödeme:** üye olmadan (misafir) ödeme; kupon alanı dikkat dağıtıyor
mu; toplam maliyet (kargo dahil) erken görünüyor mu; ödeme adım sayısı; güven
logoları (3D Secure, SSL, iyzico/PayTR vb.).

**Güven sinyalleri:** iletişim bilgileri, WhatsApp destek, KVKK/iade sayfaları,
müşteri yorumları, sosyal kanıt.

## Ticimax notu
Pek çok iyileştirme (kargo eşiği bandı, rozetler, banner, pop-up) panel
ayarlarıyla yapılabilir; düzen/şablon değişiklikleri tema kodu ister →
`ticimax-workflow` skill'ine bak.

## Çıktı
1. Huni adımı başına en kritik 3 sorun (ekran görüntüsü/URL kanıtıyla).
2. **ICE skorlu** (Impact, Confidence, Ease — 1-10) iyileştirme listesi.
3. İlk 3 öneri için A/B test hipotezi: "X'i Y yaparsak, Z metriği artar çünkü …".
