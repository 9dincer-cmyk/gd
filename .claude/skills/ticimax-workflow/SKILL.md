---
name: ticimax-workflow
description: Workflow for developing on the Ticimax e-commerce platform (www.cabani.com.tr) — theme/CSS/JS customization constraints, what requires panel access vs. what can be done from the live site, and safe rollout steps. Use when the user asks to change the site's theme, design, CSS, JS, or otherwise "geliştir" the Cabani site.
---

# Ticimax platformunda geliştirme

Ticimax, kaynak koduna doğrudan erişim vermeyen, panel üzerinden yönetilen
barındırılan (hosted) bir e-ticaret SaaS'ıdır. Claude Code bu platforma
doğrudan bağlanamaz (özel bir MCP sunucusu/API entegrasyonu kurulmadığı
sürece) — çalışma şekli buna göre farklıdır.

## Önce kontrol et: paket özellikleri açık mı?

Tema/CSS/JS düzenlemesi için Ticimax panelinde şu üçünün açık olması gerekir:
- Tasarım Yedekleme
- CSS Erişimi
- JavaScript Erişimi

Bunlar yalnızca belirli paketlerde (Special Extra Paket, OMNİ Paket, İleri
Seviye Bulut Çözümleri) bulunur. Kapalıysa, tema kodu üzerinde çalışma
yapılamaz — yalnızca panelin sunduğu hazır ayarlar (ürün/kategori metinleri,
SEO ayarları, banner'lar vb.) değiştirilebilir. Bir tema değişikliği
isteğinde önce bunu doğrula.

## Tema/kod değişikliği akışı (erişim açıksa)

1. İlgili tema dosyalarını (HTML/CSS/JS) Ticimax panelinden dışa aktarıp bu
   depoya kopyala (örn. `tema/<tema-adı>/`).
2. Değişikliği burada, Claude Code ile yap ve gözden geçir.
3. Değişikliği açıklayıcı bir commit mesajıyla bu depoya kaydet — Ticimax
   panelinin kendisi sürüm geçmişi tutmadığı için tek geri dönülebilir kayıt
   burasıdır.
4. Değişen dosyaları panele geri yükle. Mümkünse önce bir test/önizleme
   temasında dene, sonra canlıya al.
5. Canlıya aldıktan sonra etkilenen sayfaları (mobil dahil) gözle kontrol et.

## Panel erişimi gerektirmeyen işler

Aşağıdakiler tema koduna dokunmadan, canlı site URL'leri üzerinden yapılabilir
— bir değişiklik isteği bunlardan biriyse Ticimax erişimini beklemeye gerek yok:
- SEO denetimi (meta etiketler, sitemap, robots.txt, sayfa hızı, schema markup)
- İçerik/kampanya planlama, reklam metni, rakip analizi
- Reklam hesabı (Google/Meta/TikTok Ads) optimizasyonu

## Riskli adımlar

- Panele geri yükleme geri alınması kolay olmayan bir adımdır (Ticimax kendi
  sürüm geçmişini tutmaz) — canlıya almadan önce kullanıcıdan onay al.
- JavaScript enjeksiyonu (örn. bir A/B test veya analitik betiği) sitenin tüm
  sayfalarını etkileyebilir; küçük bir sayfada test etmeden geniş yayına alma.
