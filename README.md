# Телефонный сканер

Эту папку нужно публиковать как статический сайт на Netlify.

Локально файл `index.html` нельзя корректно проверять двойным кликом через `file://`: браузер блокирует manifest, service worker и часть API безопасности. Для быстрой проверки на ПК запустите локальный сервер из корня проекта:

```powershell
python -m http.server 4173 -d netlify
```

Потом откройте:

```text
http://localhost:4173/?api=ВАШ_APPS_SCRIPT_EXEC_URL
```

Для телефона нужна опубликованная HTTPS-ссылка Netlify:

```text
https://ВАШ-САЙТ.netlify.app/?api=ВАШ_APPS_SCRIPT_EXEC_URL
```
