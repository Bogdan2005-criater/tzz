### **Техническое задание для проекта Telegram-бота**

#### **Общее описание**
Необходимо разработать Telegram-бота, который предоставляет пользователю возможность сыграть в мини-игру и получить промокод. Бот должен сохранять данные пользователей в базе данных и уведомлять участников о начале раунда игры.

#### **Функциональные требования**
1. **Команда `/start`:**
   - Приветствует пользователя с сообщением:
     ```
     Добро пожаловать в AE! Сыграйте в мини-игру, чтобы получить промокод. В чат придёт уведомление, как только раунд начнётся!
     ```
   - Регистрирует пользователя в базе данных, сохраняя его Telegram ID и устанавливая начальный результат (0).

2. **Работа с базой данных:**
   - Создать базу данных `questions.db`.
   - Таблица `users` для хранения информации о пользователях:
     - `id` — уникальный идентификатор (INTEGER, PRIMARY KEY, AUTOINCREMENT).
     - `tg_id` — Telegram ID пользователя (INTEGER).
     - `high_score` — лучший результат пользователя в игре (INTEGER).

3. **Основная механика игры:**
   - Подготовить игровую механику (например, викторину или угадайку), в ходе которой пользователь может зарабатывать очки.
   - После завершения игры обновить таблицу `users` с новым результатом, если он превышает текущий рекорд.

4. **Уведомления:**
   - Бот должен уведомлять пользователей о начале нового раунда игры в индивидуальном чате.

5. **Управление данными:**
   - Обеспечить сохранение и обновление данных пользователей через функции:
     - `save_user(id, score)` — добавляет пользователя и его текущий результат в базу данных.

#### **Нефункциональные требования**
1. **Использование технологий:**
   - Язык разработки: Python.
   - Библиотека для работы с Telegram API: `aiogram`.
   - Хранение данных: SQLite.

2. **Качество кода:**
   - Структурированность: Разделение кода на модули (`main.py`, `helpers.py` и другие).
   - Простота расширения: Возможность добавить новые функции без значительных изменений в коде.

3. **Локализация:**
   - Все текстовые сообщения бота должны быть на русском языке.

#### **Рекомендации по разработке**
1. **Подготовительный этап:**
   - Установить и настроить библиотеку `aiogram`.
   - Настроить базу данных SQLite.
   - Подготовить шаблон проекта.

2. **Основной функционал:**
   - Реализовать команду `/start`.
   - Настроить базу данных для регистрации пользователей.

3. **Расширение функционала:**
   - Добавить игровую механику.
   - Реализовать систему уведомлений.
   - Добавить команду `/admin` для управления игрой и просмотра статистики.

4. **Тестирование:**
   - Проверить корректность работы команды `/start`.
   - Убедиться в правильной записи данных в базу.
   - Протестировать игровой процесс и уведомления.

---

Если нужно, можно дополнить ТЗ деталями или адаптировать его под конкретные потребности.
