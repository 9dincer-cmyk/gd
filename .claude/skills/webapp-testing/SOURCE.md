Kaynak: https://github.com/anthropics/skills/tree/main/skills/webapp-testing
(commit 34040c9). Apache 2.0 lisanslı — LICENSE.txt'ye bakın. SKILL.md, scripts/
ve examples/ değiştirilmeden kopyalandı; güncellemek için upstream'den yeniden kopyalayın.

## Cabani / bu ortama özel notlar

- Python Playwright paketi ortamda kurulu gelmeyebilir: Requirement already satisfied: playwright in /usr/local/lib/python3.11/dist-packages (1.63.0)
Requirement already satisfied: pyee<14,>=13 in /usr/local/lib/python3.11/dist-packages (from playwright) (13.0.1)
Requirement already satisfied: greenlet<4.0.0,>=3.1.1 in /usr/local/lib/python3.11/dist-packages (from playwright) (3.5.6)
Requirement already satisfied: typing-extensions in /usr/local/lib/python3.11/dist-packages (from pyee<14,>=13->playwright) (4.16.0).
  Downloading Firefox 142.0.1 (playwright build v1495)[2m from https://cdn.playwright.dev/dbazure/download/playwright/builds/firefox/1495/firefox-ubuntu-24.04.zip[22m
Downloading Firefox 142.0.1 (playwright build v1495)[2m from https://playwright.download.prss.microsoft.com/dbazure/download/playwright/builds/firefox/1495/firefox-ubuntu-24.04.zip[22m
Downloading Firefox 142.0.1 (playwright build v1495)[2m from https://cdn.playwright.dev/builds/firefox/1495/firefox-ubuntu-24.04.zip[22m
Downloading Firefox 142.0.1 (playwright build v1495)[2m from https://cdn.playwright.dev/dbazure/download/playwright/builds/firefox/1495/firefox-ubuntu-24.04.zip[22m
Downloading Firefox 142.0.1 (playwright build v1495)[2m from https://playwright.download.prss.microsoft.com/dbazure/download/playwright/builds/firefox/1495/firefox-ubuntu-24.04.zip[22m
Failed to install browsers
Error: Failed to download Firefox 142.0.1 (playwright build v1495), caused by
Error: Download failure, code=1
    at ChildProcess.<anonymous> (/opt/node22/lib/node_modules/playwright/node_modules/playwright-core/lib/server/registry/browserFetcher.js:94:32)
    at ChildProcess.emit (node:events:519:28)
    at ChildProcess._handle.onexit (node:internal/child_process:293:12) ÇALIŞTIRMAYIN — Chromium önceden kurulu; pip sürümü
  farklı bir tarayıcı sürümü beklediği için başlatırken yolu açıkça verin:
  
- Örneklerdeki  ve  yollarını scratchpad
  dizininizle değiştirin.
- Tipik kullanım:  altında düzenlenen HTML/CSS/JS'i panele yüklemeden
  önce  ile açıp 390×844 (mobil) ve 1440×900 (masaüstü) ekran
  görüntüsü almak, konsol hatalarını yakalamak.
- Canlı site () için bulut ortamının ağ politikasında bu
  alan adına izin verilmiş olmalı; yoksa  alınır.
- Canlı sitede yalnızca okuma/gezinme yapın: sipariş, ödeme, üyelik veya
  form gönderimi yok.
