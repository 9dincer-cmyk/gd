---
name: product-sorting
description: Merchandising and product ordering for Cabani category and home pages — scoring products by sales, conversion, margin, stock, and newness to decide default sort order, pinned products, featured/best-seller blocks, and cross-sell. Use when the user asks for ürün sıralaması, vitrin düzeni, hangi ürün üstte olmalı, çok satanlar bloğu, or merchandising.
---

# Ürün sıralaması & vitrin (merchandising)

## 1. Veri
Kullanıcıdan (Ticimax rapor dışa aktarımı / Supermetrics GA4) ürün bazında iste,
son 30-90 gün: ürün kodu, kategori, görüntülenme (GA4 `view_item`), sepete
ekleme, satış adedi, ciro, brüt marj, stok adedi, beden/varyant stok
kapsaması, eklenme tarihi, iade oranı. Eksik sütunla devam et ama ağırlığı sıfırla ve belirt.

## 2. Sıralama skoru (0-100)
Her metriği kategori içinde yüzdelik sıraya çevir (0-1), sonra ağırlıklandır:
| Bileşen | Varsayılan ağırlık |
|---|---|
| Satış hızı (adet/gün) | 0.30 |
| Dönüşüm oranı (satış / görüntülenme, min. 100 görüntülenme) | 0.20 |
| Birim brüt kâr | 0.20 |
| Stok sağlığı (adet + beden kapsaması; tek beden kalmışsa düşür) | 0.15 |
| Yenilik (son 30 gün eklenen ürüne destek) | 0.10 |
| İade oranı (ters) | 0.05 |
Ağırlıklar hedefe göre değişir: stok eritme → stok ağırlığını artır; kâr
odaklı → marj; yeni sezon → yenilik. Hesabı Python/pandas ile yap, sonucu
CSV/XLSX olarak ver (`anthropic-skills:xlsx`).

## 3. Kurallar (skorun üstüne)
- Stoğu biten veya ana bedenleri tükenmiş ürün ilk 2 satırda olmasın.
- İlk sırada renk/model çeşitliliği: aynı modelin 3 rengini yan yana dizme.
- Az görüntülenmiş yeni ürünlere "keşif" alanı: ilk 12-24 ürün içinde 2-4 yer.
- Kampanyadaki ürünler kampanya kategorisinde üstte, genel kategoride skorla.

## 4. Ticimax'ta uygulama
Kategori ürün sıralaması / vitrin ve "öne çıkan" alanları panelden ayarlanır
(sıra numarası veya varsayılan sıralama kriteri). Çıktıyı panele girilecek
sıra numaralarıyla ver; uygulamayı kullanıcı yapar.

## Çıktı
Kategori başına: sıralı ürün listesi (sıra | ürün | skor | öne çıkan neden),
ana sayfa vitrini ve "çok satanlar" bloğu önerisi, çapraz satış eşleşmeleri,
iki haftalık A/B/önce-sonra ölçüm planı (kategori dönüşüm oranı, ürün başı ciro).
