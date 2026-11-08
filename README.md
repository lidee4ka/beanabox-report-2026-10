# BEANABOX · продуктовый отчёт · апрель — октябрь 2026

Пакет для **GitHub Pages** (как сентябрьский `beanabox-report` / catalog redesign).

## Содержимое

- `index.html` — отчёт (Gilroy + Chart.js с CDN)
- `favicon.svg` — как у [beanabox-catalog-redesign](https://lidee4ka.github.io/beanabox-catalog-redesign/)
- `fonts/` — локальный Gilroy
- `.nojekyll` — отключает Jekyll на Pages

## Как выложить

1. Создайте **пустой** репозиторий на GitHub, например `beanabox-report-2026-10`
   (или обновите существующий сентябрьский репо новой папкой/веткой — как удобнее).
2. Залейте **содержимое этой папки** в корень репозитория:

```bash
cd github-pages
git init
git add .
git commit -m "Publish BEANABOX product report Apr–Oct 2026"
git branch -M main
git remote add origin https://github.com/<USER>/<REPO>.git
git push -u origin main
```

Если репозиторий уже есть (не `git init`):

```bash
cd github-pages
git clone https://github.com/<USER>/<REPO>.git tmp-repo
# скопировать файлы из github-pages поверх tmp-repo (кроме .git)
git -C tmp-repo add .
git -C tmp-repo commit -m "Publish BEANABOX product report Apr–Oct 2026"
git -C tmp-repo push
```

3. GitHub → **Settings → Pages** → Source: **Deploy from a branch** → Branch: `main` / root → Save.
4. Через 1–2 минуты: `https://<USER>.github.io/<REPO>/`.

## Важно

- В пакет **не** входят токены, дампы Strapi, сырые JSON и скрипты сборки.
- Chart.js грузится с jsDelivr — нужен интернет у читателя.
- Логотип в шапке — с Tilda CDN; при офлайне может не показаться.
- Gilroy: убедитесь, что лицензия позволяет публичный веб.
- Исходник для правок: `../build_october_html.py` → `python build_october_html.py` → снова этот скрипт `_pack_github_pages.py`.
