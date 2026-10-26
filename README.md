# ВМН.exe — интерактивный сайт

## Локальный запуск (Windows / PowerShell)

```powershell
py -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe app.py
```

Откройте http://127.0.0.1:5000

## Публикация на Render

1. Распакуйте архив и загрузите все файлы проекта в GitHub-репозиторий.
2. Откройте https://render.com и выберите **New + → Blueprint**.
3. Подключите репозиторий, в котором лежит `render.yaml`, и подтвердите создание сервиса.
4. После завершения деплоя откройте публичный URL Render — сайт будет доступен другим людям с телефона и компьютера.

Если Blueprint недоступен, создайте **New + → Web Service** и укажите:
- Build Command: `pip install -r requirements.txt`
- Start Command: `gunicorn app:app`

Сайт не требует базы данных или API. Он адаптируется к экрану телефона. Прогресс хранится в открытой странице; перезагрузка начинает игру заново.
