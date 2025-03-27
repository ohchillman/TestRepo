# Система автоматизированного управления контентом для социальных сетей

Комплексная система для автоматизации полного цикла работы с контентом в социальных сетях - от парсинга актуальных новостей до их персонализированного размещения в различных аккаунтах с учетом tone of voice.

## Обзор проекта

Система обеспечивает автоматизированное управление контентом для 13 аккаунтов в четырех социальных сетях:
- Twitter
- LinkedIn
- YouTube Blog
- Threads

## Архитектура системы

Система состоит из трех основных компонентов:

1. **Модуль парсинга новостей** (Python)
   - Сбор данных из 4 новостных источников
   - Фильтрация релевантных новостей
   - Обход защиты от парсинга
   - Технологии: Python, BeautifulSoup, requests, Selenium

2. **Модуль рерайта контента** (Make.com + OpenAI API)
   - Создание 13 уникальных версий каждой новости
   - Адаптация контента под разные аккаунты
   - Проверка качества сгенерированного текста
   - Технологии: Make.com, OpenAI API

3. **Модуль автопостинга** (PHP + Selenium)
   - Размещение контента в 4 социальных сетях
   - Эмуляция человеческого поведения
   - Обход антифрод-защиты
   - Технологии: PHP, Selenium, Dolphin Anty
   - Использование прокси-серверов (1 IP на аккаунт)

## Структура проекта

```
social_media_automation/
├── config/                  # Конфигурационные файлы
├── docs/                    # Документация
├── logs/                    # Директория для логов
├── public/                  # Публичная директория
├── src/                     # Исходный код
│   ├── Application.php      # Основной класс приложения
│   ├── Controllers/         # Контроллеры
│   ├── Core/                # Ядро системы
│   ├── Parsers/             # Компоненты для парсинга новостей
│   ├── parsers/             # Python-скрипты для парсинга
│   ├── Rewrite/             # Компоненты для рерайта контента
│   └── Posting/             # Компоненты для публикации контента
├── tests/                   # Тесты
├── vendor/                  # Зависимости PHP (Composer)
├── composer.json            # Конфигурация Composer
└── cli.php                  # Точка входа для CLI
```

## Текущий статус проекта

Проект полностью разработан и готов к использованию. Все компоненты системы успешно прошли тестирование:
- Модуль парсера новостей: УСПЕШНО
- Система рерайта контента: УСПЕШНО
- Система автопостинга: УСПЕШНО
- Интеграция компонентов: УСПЕШНО
- Веб-интерфейс: УСПЕШНО

## Требования

- PHP >= 7.4
- Python 3.x с установленными библиотеками BeautifulSoup, requests, Selenium
- Доступ к API Make.com и OpenAI
- Dolphin Anty для управления профилями браузера
- Прокси-сервера (1 IP на аккаунт)

## Установка и настройка

1. Клонировать репозиторий:
   ```
   git clone https://github.com/ohchillman/TestRepo.git
   cd TestRepo
   ```

2. Установить зависимости PHP:
   ```
   composer install
   ```

3. Настроить конфигурационный файл:
   ```
   cp config/.env.example config/.env
   ```
   Отредактировать файл `.env`, указав необходимые параметры доступа к API и базе данных.

4. Установить зависимости Python:
   ```
   pip install beautifulsoup4 requests selenium
   ```

5. Настроить доступы к социальным сетям и прокси в соответствующих конфигурационных файлах.

## Использование

### Веб-интерфейс

Для запуска веб-интерфейса необходимо настроить веб-сервер (Apache/Nginx) с корневой директорией в `public/`.

### Командная строка

Для запуска через командную строку используйте:

```
php cli.php [command] [options]
```

Доступные команды:
- `parse` - запуск парсинга новостей
- `rewrite` - запуск рерайта контента
- `post` - запуск автопостинга
- `workflow` - запуск полного цикла (парсинг → рерайт → постинг)

## Документация

Подробная документация доступна в директории `docs/`:

- [Руководство по развертыванию](docs/deployment.md)
- [Руководство пользователя](docs/user_manual.md)
- [Техническая документация](docs/technical.md)

## Планы по развитию

1. **Расширение поддержки социальных сетей**
   - Добавление поддержки Facebook
   - Добавление поддержки Instagram
   - Добавление поддержки TikTok

2. **Улучшение системы рерайта**
   - Интеграция с другими AI-сервисами
   - Добавление возможности создания собственных шаблонов tone of voice
   - Реализация обучения на основе обратной связи

3. **Расширение возможностей парсинга**
   - Добавление поддержки RSS-фидов
   - Реализация парсинга видеоконтента
   - Добавление возможности парсинга комментариев

4. **Улучшение веб-интерфейса**
   - Разработка мобильной версии
   - Добавление дашбордов с аналитикой
   - Реализация системы уведомлений

5. **Оптимизация производительности**
   - Внедрение системы кэширования
   - Оптимизация запросов к API социальных сетей
   - Реализация асинхронной обработки задач

## Авторы

- Manus Agent <manus@example.com>

## Лицензия

Этот проект распространяется под лицензией [MIT](LICENSE).
