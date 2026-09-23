Kaynak: https://github.com/anthropics/skills/tree/main/skills/webapp-testing
(commit 34040c9). Apache 2.0 lisanslı — LICENSE.txt'ye bakın. SKILL.md, scripts/
ve examples/ değiştirilmeden kopyalandı; güncellemek için upstream'den yeniden kopyalayın.

## Cabani / bu ortama özel notlar

- Python Playwright paketi ortamda kurulu gelmeyebilir: `pip install playwright`.
  `playwright install` ÇALIŞTIRMAYIN — Chromium önceden kurulu ve tarayıcı
  indirme sunucuları ağ politikasınca engelli. pip sürümü farklı bir tarayıcı
  sürümü beklediği için başlatırken yolu açıkça verin:
  `p.chromium.launch(headless=True, executable_path='/opt/pw-browsers/chromium')`
- Örneklerdeki `/mnt/user-data/outputs/` ve `/tmp/` yollarını scratchpad
  dizininizle değiştirin.
- Tipik kullanım: `tema/` altında düzenlenen HTML/CSS/JS'i panele yüklemeden
  önce `file://` ile açıp 390×844 (mobil) ve 1440×900 (masaüstü) ekran
  görüntüsü almak, konsol hatalarını yakalamak.
- Canlı site (`www.cabani.com.tr`) için bulut ortamının ağ politikasında bu
  alan adına izin verilmiş olmalı; yoksa `ERR_TUNNEL_CONNECTION_FAILED` alınır.
- Canlı sitede yalnızca okuma/gezinme yapın: sipariş, ödeme, üyelik veya
  form gönderimi yok.
