
## Запуск проекта Laravel

### 1. Установка Laravel

Установить Laravel внутри контейнера:

```bash
docker compose exec app composer create-project laravel/laravel .
```

### 2. Установка зависимостей Laravel

```bash
# Установка PHP зависимостей
docker compose exec app composer install

# Генерация ключа приложения (Если APP_KEY в .env пустой)
docker compose exec app php artisan key:generate

# Применение миграций
docker compose exec app php artisan migrate
```

```bash
# Проверка версии Laravel
docker compose exec app php artisan --version
```

### 3. Полезные команды

```bash
# Просмотр логов
docker compose logs -f app

# Остановка контейнеров
docker compose down

# Перезапуск контейнеров
docker compose restart

# Выполнение artisan команд внутри контейнера
docker compose exec app php artisan <command>

# Подключение к базе данных
docker compose exec db psql -U postgres -d laravel
```

### 4. Проблемы с правами доступа

```bash
docker compose exec app chown -R www-data:www-data /var/www/html
```
