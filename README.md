# gumroad-board

Приватный дашборд продаж JetMetrics на Gumroad. Хостится на GitHub Pages под паролём.

## Как устроено
- `index.html` — дашборд (открытый код, данных внутри нет). Правится через git.
- `sales.json` — зашифрованные данные (AES-256-CBC, пароль). Пишет Apps Script в конце синка Gumroad.
- Открываешь Pages-URL → вводишь пароль → браузер расшифровывает sales.json → рендер.

## Данные
Источник правды — Google Sheet проекта. Apps Script (`syncGumroadSales` → `exportSalesToGitHub`)
шифрует данные паролём `DASH_PASSWORD` и пушит `sales.json` сюда. UI данных не хранит.

## Источник дашборда
`Maria/work/gumroad dashboard/dashboard.html` — правь там, копируй в `index.html`, пушь.
