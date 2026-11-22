SKY HOP — NETLIFY

Это исходный проект для Netlify: сайт + две serverless functions + Netlify Blobs для постоянных рекордов.

ВАЖНО: простой drag-and-drop ZIP в Netlify Drop может НЕ выполнить npm install и сборку Functions. Надёжный способ:
1. Распакуй архив и загрузи папку в репозиторий GitHub.
2. Netlify -> Add new project -> Import an existing project -> GitHub -> выбери репозиторий.
3. Netlify прочитает netlify.toml и соберёт Functions, установив зависимости.
4. После деплоя открой https://ТВОЙ-САЙТ.netlify.app/ и https://ТВОЙ-САЙТ.netlify.app/api/leaderboard.
5. Пришли адрес сайта в чат, чтобы записать его в SkyHop_Online.html.

POST /api/score JSON: {"nick":"Владислав","token":"0123456789abcdef0123456789abcdef","score":120}
GET /api/leaderboard возвращает массив {nick,best}.

Внимание: без проверки результатов сервером рейтинг можно накрутить. Токен — идентификатор, не защищённая учётная запись. Одновременные запросы могут вызвать гонку обновления рекорда.
