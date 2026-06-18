# Телефонный сканер

Статический сайт публикуется на GitHub Pages из этой папки через
`.github/workflows/deploy-pages.yml`.

Локально файл `index.html` нельзя корректно проверять двойным кликом через `file://`: браузер блокирует manifest, service worker и часть API безопасности. Для быстрой проверки на ПК запустите локальный сервер из корня проекта:

```powershell
python -m http.server 4173 -d netlify
```

Потом откройте на ПК:

```text
http://localhost:4173/?api=ВАШ_APPS_SCRIPT_EXEC_URL
```

Для телефона нужна опубликованная HTTPS-ссылка GitHub Pages:

```text
https://ВАШ-ЛОГИН.github.io/ИМЯ-РЕПОЗИТОРИЯ/?api=ВАШ_APPS_SCRIPT_EXEC_URL
```

## Публикация

1. Загрузите весь проект в репозиторий GitHub.
2. В репозитории откройте `Settings` → `Pages`.
3. В поле `Source` выберите `GitHub Actions`.
4. Отправьте изменения в ветку `main` или `master`.
5. Дождитесь зеленого workflow `Deploy mobile app to GitHub Pages`.

После первого открытия с параметром `?api=...` адрес Apps Script сохранится на телефоне.
Камеру нужно разрешить в Safari или Chrome. Страница должна быть открыта напрямую,
не внутри iframe.
