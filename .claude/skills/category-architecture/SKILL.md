---
name: category-architecture
description: Designing and improving Cabani's site category structure — menu/navigation, category hierarchy, filters (beden/renk/fiyat/materyal), landing/collection pages, naming based on Turkish search demand, and redirects when restructuring. Use when the user asks for kategori önerisi, menü düzeni, yeni kategori/koleksiyon açma, filtre yapısı, or site mimarisi.
---

# Kategori yapısı & site mimarisi

## 1. Mevcut durumu çıkar
- Canlı sitenin menüsünü ve kategori URL'lerini tara (ana sayfa HTML + sitemap.xml).
- Her kategori için ürün sayısı (sayfadaki ürün adedi), boş/çok az ürünlü
  (< 8) ve aşırı kalabalık (> 200, alt kırılım gerektiren) kategorileri işaretle.

## 2. Talep verisiyle adlandır
- Kategori adları müşterinin aradığı kelimelerle olmalı (iç jargon değil).
  Semrush bağlıysa `keyword_research` (tr) ile hacim al; yoksa Google
  otomatik tamamlama / Google Trends ile karşılaştır.
- Aranan ama karşılığı olmayan niş ifadeler → yeni alt kategori veya
  **koleksiyon/landing sayfası** adayı (ör. "keten gömlek", "düğün için elbise").

## 3. Tasarım ilkeleri
- En fazla 3 seviye derinlik; her ürün ≤ 3 tıkta.
- Menüde 5-8 ana kategori; "Yeni Gelenler", "Çok Satanlar", "İndirim"
  gibi ticari koleksiyonlar menüde görünür olsun.
- Aynı ürün birden fazla kategoride olabilir, ama canonical tek olmalı.
- Filtreler: kategoriye özgü (giyimde beden, renk, fiyat, materyal, kalıp);
  filtre sayfaları indekslenmesin (noindex/canonical) — sadece talebi olan
  kombinasyonlar ayrı kategori olsun.
- Mevsimsel/kampanya koleksiyonları için kalıcı URL kullan (her yıl yeniden
  kullanılır, SEO değeri birikir).

## 4. Değişiklik yaparken
- URL değişen/silinen her kategori için **301 yönlendirme listesi** hazırla
  (eski URL → yeni URL). Ticimax panelinde yönlendirme tanımlanır.
- Her kategoriye özgün açıklama metni ve meta etiket (`product-content-tr`).

## Çıktı
Önerilen ağaç (girintili liste) + değişiklik tablosu **(Mevcut | Önerilen |
Gerekçe/arama hacmi | Aksiyon: yeni/birleştir/yeniden adlandır/sil | 301)**.
