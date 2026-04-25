# 🏠 Парсер объявлений о недвижимости

Извлекает структурированные данные из объявлений о недвижимости с помощью Claude AI.

---

## Локальный запуск

### 1. Установи зависимости
```bash
npm install
```

### 2. Создай файл `.env` и добавь API-ключ
```
ANTHROPIC_API_KEY=sk-ant-...
```
> Ключ можно получить на [console.anthropic.com](https://console.anthropic.com)

### 3. Запусти сервер
```bash
npm start
```

Открой браузер: **http://localhost:3000**

---

## Деплой на Railway (бесплатно, публичная ссылка)

### 1. Залей проект на GitHub
```bash
git init
git add .
git commit -m "init"
git remote add origin https://github.com/ТВО_ИМЯ/listing-parser.git
git push -u origin main
```

### 2. Зарегистрируйся на [railway.app](https://railway.app)

### 3. Создай новый проект
- New Project → Deploy from GitHub repo
- Выбери свой репозиторий

### 4. Добавь переменную окружения
- Перейди в Settings → Variables
- Добавь: `ANTHROPIC_API_KEY` = `sk-ant-...`

### 5. Готово!
Railway автоматически запустит `npm start` и выдаст публичную ссылку вида:
`https://listing-parser-production.up.railway.app`

---

## Структура проекта

```
listing-parser/
├── server.js        # Express сервер (прокси к Claude API)
├── package.json
├── .gitignore
├── .env             # API-ключ (не коммитить!)
└── public/
    └── index.html   # Фронтенд
```

## Как это работает

```
Браузер → /api/parse → server.js → Claude API → ответ обратно
```

Сервер хранит API-ключ в безопасности — никто снаружи его не видит.
