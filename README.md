Для корректной работы необходимо установить библиотеки: requests, json, sqlite3, datetime, pyTelegramBotAPI 

Для полной работы используются 4 файла:

* main.py
** Получает данные с предложениями в виде JSON.
** Проходит по каждому предложению в списке.
** Извлекает данные и  и передает их функции check_database в realt.py, которая сохраняет данные в базе данных.

* realt.py
** Проверяет, существует ли предложение (по ID) в базе данных SQLite.
** Выполняет SQL-запрос для проверки существования offer_id в таблице offers.
** Вставляет новое предложение в базу данных с помощью SQL-запроса.

* bot.py
** Обрабатывает команду /start.
** Получает chat_id пользователя, который отправил команду.
** Выполняется SQL-запрос, который выбирает все URL из таблицы offers.
** Извлекает и отправляет данные из базы.

* create_bd.py в каталоге .venv/db
** Создает таблицу offers в базе данных SQLite с помощью библиотеки sqlite3.
