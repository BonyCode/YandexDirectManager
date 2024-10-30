# YandexDirectManager

**YandexDirectManager** - десктопное приложение для управления ставками и рекламными кампаниями в Яндекс.Директ. Программа оптимизирует расходы, поддерживает удержание позиций по минимальной цене, предлагает аналитику и управление в режиме реального времени. Интерфейс разработан с использованием Electron, что делает его кросс-платформенным и удобным для пользователей.

## Основные функции

1. **Автоматическое удержание позиций** - обновление ставок через API Яндекс.Директ с частотой раз в минуту для поддержания объявлений на первой странице по минимальной цене.
2. **Оптимизация расходов** - позволяет экономить до 50% рекламного бюджета за счет эффективного управления ставками и настройки стратегий.
3. **Поддержка нескольких аккаунтов** - работает как с агентскими, так и с прямыми аккаунтами Яндекс.Директ.
4. **Аналитика и статистика** - отображение данных в реальном времени в виде таблиц и графиков, экспорт данных в Excel (CSV).
5. **Гибкая настройка стратегий** - возможность создания и применения индивидуальных стратегий для каждой рекламной кампании.
6. **Многопользовательская поддержка** - разграничение прав доступа для администраторов, клиентов и представителей.
7. **Поддержка настраиваемых графиков** - интерфейс для анализа и визуализации данных о показах, кликах и расходах с использованием линейных и столбчатых диаграмм.

## Технологии

- **Frontend**: Electron для графического интерфейса, Chart.js/D3.js для построения кастомных графиков.
- **Backend**: Java для обработки бизнес-логики, многопоточной обработки данных и взаимодействия с API Яндекс.Директ.
- **База данных**: PostgreSQL для хранения данных о кампаниях, пользователях и ставках.
- **API**: API Яндекс.Директ для получения и обновления данных о рекламных кампаниях.
- **Socket/WebSocket**: Для обновления данных в реальном времени.

## Основные элементы интерфейса

### Главный график
- **Описание**: График показывает динамику расходов, показов и кликов для выбранной кампании или группы кампаний. Поддерживаются линейные и столбчатые диаграммы.
- **Реализация**: Использование Chart.js или D3.js для визуализации данных с настройкой временных интервалов.

### Боковая панель с инструментами
- **Описание**: Доступ к инструментам управления кампаниями и настройке стратегий.
- **Реализация**: Кнопки и выпадающие меню для управления кампаниями, настройки фильтров и выбора стратегий.

### Панель временных интервалов
- **Описание**: Переключение временных интервалов (1 день, 1 неделя, 1 месяц и т.д.) для отображения статистики кампаний.
- **Реализация**: Горизонтальное меню с кнопками, данные обновляются через API по выбранному интервалу.

### Панель статистики
- **Описание**: Таблицы и диаграммы для анализа ключевых показателей (показы, клики, расходы, CTR) по выбранным кампаниям.
- **Реализация**: Таблицы с данными и графики, обновляемые через WebSocket или API, с возможностью экспорта в Excel.

### Информация о текущей активности кампании
- **Описание**: Панель с текущими показателями, включая расход, клики, показы и уровень конверсии.
- **Реализация**: Обновление текстовых элементов в реальном времени с цветовой индикацией для отображения изменений.

## Установка и запуск

### Системные требования

- **ОС**: Windows, macOS или Linux.
- **Node.js**: Версия 14 или выше для запуска Electron.
- **Java**: Версия 17 или выше для выполнения бизнес-логики.
- **PostgreSQL**: Для хранения данных.

### Установка

1. **Склонируйте репозиторий**:

    ```bash
    git clone https://github.com/yourusername/YandexDirectManager.git
    cd YandexDirectManager
    ```

2. **Установите зависимости для Electron**:

    ```bash
    npm install
    ```

3. **Настройте базу данных PostgreSQL**:
   - Создайте базу данных и пользователя PostgreSQL.
   - Выполните SQL-скрипты в `/database/setup.sql` для создания необходимых таблиц.

4. **Настройте переменные окружения**:
   - Создайте файл `.env` в корне проекта и укажите настройки базы данных, токен API Яндекс.Директ и другие ключевые параметры:

    ```plaintext
    DB_HOST=localhost
    DB_PORT=5432
    DB_USER=yourusername
    DB_PASS=yourpassword
    DB_NAME=yandex_direct_manager
    YANDEX_API_TOKEN=your_yandex_direct_api_token
    ```

5. **Запустите backend (Java)**:
   - Соберите и запустите Java-приложение:

    ```bash
    ./gradlew build
    java -jar build/libs/YandexDirectManager.jar
    ```

6. **Запустите приложение Electron**:

    ```bash
    npm start
    ```

## Использование

### Основные действия в интерфейсе

- **Добавление и настройка аккаунтов**: Перейдите в раздел "Аккаунты" для добавления новых аккаунтов Яндекс.Директ и настройки токенов.
- **Просмотр и управление кампаниями**: В разделе "Ставки" и "Стратегии" доступны данные о кампаниях, ставки и настройки стратегий.
- **Анализ данных**: Раздел "Статистика" включает таблицы и графики для анализа данных по выбранным кампаниям.
- **Настройка графика и временных интервалов**: На главной странице выберите временной интервал и настройте отображение данных.

### Экспорт данных
- Данные могут быть экспортированы в формат Excel (CSV) из раздела "Статистика" с помощью кнопки "Экспортировать".

## Разработка

### Основные библиотеки и инструменты

- **Electron**: для создания кросс-платформенного интерфейса.
- **React или Vue** (по желанию): для управления состоянием и компонентами в интерфейсе.
- **Java**: для основной бизнес-логики и интеграции с API.
- **Chart.js или D3.js**: для построения графиков и диаграмм.
- **PostgreSQL**: для хранения данных о кампаниях и пользователях.
- **Apache POI**: для экспорта данных в Excel.
- **JFreeChart**: для построения графиков статистики (в Java).
