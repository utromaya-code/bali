# Соль. Рис. Тишина. — Бали и Гили Мено, 12–22 февраля 2027

Лендинг путешествия-практики. Статический сайт, публикуется через GitHub Pages
прямо из корня ветки `main`.

## Что где

| Путь | Что это |
| --- | --- |
| `index.html`, `styles.css`, `script.js`, `images/` | опубликованный сайт |
| `_src/content.json` | весь текст, даты, цены, фото и настройки |
| `_src/scripts/build_bali.py` | собирает `index.html` из `content.json` |
| `_src/scripts/prepare_bali_photos.py` | кадрирует и тонирует фото в `images/` |
| `_src/scripts/bali_map.py` | рисует карту маршрута |
| `_src/telegram-bot/` | пересылка заявок с формы в Telegram (Cloudflare Worker) |

Папки с подчёркиванием GitHub Pages не публикует, поэтому `_src/` на сайт
не попадает.

## Как поменять текст

1. Правка в `_src/content.json`.
2. `python3 _src/scripts/build_bali.py`
3. Коммит и пуш в `main` — сайт обновится через минуту.

## Свой домен

1. Файл `CNAME` в корне с одной строкой — доменом (сейчас `bali-soul.ru`).
2. В DNS у регистратора: четыре A-записи на `185.199.108.153`,
   `185.199.109.153`, `185.199.110.153`, `185.199.111.153` и CNAME `www` →
   `utromaya-code.github.io`.
3. Settings → Pages → Enforce HTTPS.
4. В `content.json` поменять `meta.siteUrl` и `meta.noindex: false`, пересобрать.
