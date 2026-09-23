---
name: campaign-ideas
description: Generating concrete, margin-safe promotion and campaign ideas for Cabani — offer mechanics (sepette indirim, 2. ürün, kargo bedava eşiği, paket/bundle, hediye, sadakat), which products/categories to put on promo, and how to launch them in Ticimax. Use when the user asks for kampanya önerisi, "ne kampanyası yapalım", promosyon fikri, stok eritme, or sepet ortalamasını artırma.
---

# Kampanya önerileri

`campaign-calendar-tr` **ne zaman** sorusunu, bu skill **ne** sorusunu cevaplar.

## 1. Önce veri iste (yoksa varsayımı açıkça yaz)
- Brüt marj (kategori bazında), ortalama sepet tutarı (AOV), mevcut ücretsiz kargo eşiği.
- Ürün satış raporu (Ticimax → Raporlar → ürün satış / stok): son 90 gün
  adet, ciro, stok adedi, stokta kalma gün sayısı.
- Hedef: ciro mu, yeni müşteri mi, stok eritme mi, AOV artışı mı? Tek ana hedef seç.

## 2. Hedefe göre kampanya mekaniği
| Hedef | Mekanik | Dikkat |
|---|---|---|
| AOV artışı | Kargo bedava eşiğini AOV'nin ~%20-30 üstüne koy; "X TL üzeri %10"; kademeli indirim (1500 TL'ye %10, 2500'e %15) | Eşik altı sepete "şunu ekle" önerisi |
| Stok eritme | Yavaş dönen ürünlerde 2. ürün %50, outlet kategorisi, paket (bundle) | Çok satanları indirime sokma |
| Yeni müşteri | İlk siparişe kupon (e-posta/WhatsApp kaydı karşılığı), influencer kodu | Kupon suistimali: tek kullanım, üyeye bağlı |
| Tekrar satın alma | Sipariş sonrası 30 gün geçerli kupon, sadakat puanı, geri kazanma e-postası | Klaviyo akışlarıyla otomatikleştir |
| Marka algısı | Hediye paketi, sınırlı koleksiyon, ön sipariş | İndirim yerine değer katma |

## 3. Marj kontrolü (her öneri için hesapla)
`Kampanya sonrası marj = (fiyat × (1 − indirim) − maliyet) / (fiyat × (1 − indirim))`
İndirimin başabaşı için gereken ek satış: `indirim / (marj − indirim)`
(ör. %40 marjda %20 indirim → aynı kârı korumak için satışın **2 katına** çıkması gerekir).
Bunu tabloda göster; marjı eriten öneriyi "önerilmez" diye işaretle.

## 4. Ticimax'ta uygulama
Kampanya / kupon / sepette indirim / kargo eşiği tanımları panelden yapılır
(Pazarlama → Kampanyalar, Kupon Kodları). Banner ve kampanya kategorisi
gerekiyorsa `ticimax-workflow`'a bak. Panelde değişikliği kullanıcı yapar.

## Çıktı
3-5 kampanya kartı: **Ad · Hedef · Mekanik · Kapsam (ürün/kategori) · Süre ·
Marj etkisi · Kanallar (Meta, e-posta, site banner) · Başarı metriği**.
Yasal: "önceki fiyat" = son 30 günün en düşük fiyatı; kampanya koşulları açıkça yazılmalı.
