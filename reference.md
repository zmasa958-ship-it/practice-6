# Справка

**Разделы документации:**

[Главная](index.md) | [Быстрый старт](quick-start.md) | [Установка](installation.md) | [Руководство](user-guide.md) | [Справка](reference.md) | [Неисправности](troubleshooting.md)

---

## Роли

| Роль | Каталог | Поиск / фильтр | Товары (CRUD) | Заказы |
|------|---------|----------------|---------------|--------|
| Гость | Просмотр | Ограничен / нет | Нет | Нет |
| Клиент | Просмотр | Ограничен | Нет | Свои (если реализовано) |
| Менеджер | Просмотр | Да | Нет | Просмотр / ведение (по правам) |
| Администратор | Полный | Да | Добавление / изменение / удаление | Полный доступ |

<a id="роли"></a>

## Основные модули

| Компонент | Описание |
|-----------|----------|
| `main.py` | Точка входа приложения (GUI на Flet) |
| `database.py` | Слой доступа к данным (класс `Database`, psycopg2) |
| `config.py` | Параметры подключения к БД |
| `modules/` | Модули интерфейса и бизнес-логики |
| `assets/` | Изображения товаров и иконки |
| `requirements.txt` | Зависимости Python |
| `venv/` | Виртуальное окружение |

## Полезные команды (Windows)

### Виртуальное окружение

```bat
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

### Запуск приложения

```bat
venv\Scripts\activate
python main.py
```

### Проверка службы PostgreSQL

```bat
sc query postgresql-x64-15
net start postgresql-x64-15
```

### Проверка базы данных

```bat
psql -h localhost -U postgres -d shoe_store -c "SELECT COUNT(*) FROM tovar;"
```

### Резервное копирование базы

```bat
pg_dump -h localhost -U postgres -d shoe_store -F c -f C:\backup\shoe_store\shoe_store_backup.dump
```

### Проверка свободного места на диске

```bat
wmic logicaldisk get size,freespace,caption
```

## Конфигурация (`config.py`)

Параметры подключения хранятся в `DB_CONFIG` (host, port, database, user, password).  
После изменения перезапустите приложение.

## Сеть

| Ресурс | Порт / примечание |
|--------|-------------------|
| PostgreSQL | TCP **5432** |
| Локальная БД на том же ПК | Внешний сетевой доступ не требуется |

---

[← Назад: Руководство](user-guide.md) | [Далее: Неисправности →](troubleshooting.md)
