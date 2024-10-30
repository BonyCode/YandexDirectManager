# YandexDirectManager

**YandexDirectManager** — десктопное приложение для управления ставками и рекламными кампаниями в Яндекс.Директ. Программа оптимизирует расходы, поддерживает удержание позиций по минимальной цене, предлагает аналитику и управление в режиме реального времени. Интерфейс разработан с использованием Electron, что делает его кросс-платформенным и удобным для пользователей.

## Основные функции

1. **Автоматическое удержание позиций** — обновление ставок через API Яндекс.Директ с частотой раз в минуту, для поддержания объявлений на первой странице по минимальной цене.
2. **Оптимизация расходов** — позволяет экономить до 50% рекламного бюджета за счет эффективного управления ставками и настройки стратегий.
3. **Поддержка нескольких аккаунтов** — работает как с агентскими, так и с прямыми аккаунтами Яндекс.Директ.
4. **Аналитика и статистика** — отображение данных в реальном времени в виде таблиц и графиков, экспорт данных в Excel (CSV).
5. **Гибкая настройка стратегий** — возможность создания и применения индивидуальных стратегий для каждой рекламной кампании.
6. **Многопользовательская поддержка** — разграничение прав доступа для администраторов, клиентов и представителей.
7. **Поддержка TradingView Charting** — интерфейс для анализа и прогнозирования курсов с использованием свечных и линейных графиков.

## Технологии

- **Frontend**: Electron для графического интерфейса, TradingView Charting Library (или Chart.js/D3.js для кастомных графиков).
- **Backend**: Java для обработки бизнес-логики, многопоточной обработки данных и взаимодействия с API Яндекс.Директ.
- **База данных**: PostgreSQL для хранения данных о кампаниях, пользователях и ставках.
- **API**: API Яндекс.Директ для получения и обновления данных о рекламных кампаниях.
- **Socket/WebSocket**: Для обновления данных в реальном времени.

## Использование

### Основные действия в интерфейсе

- **Добавление и настройка аккаунтов**: Перейдите в раздел "Аккаунты" для добавления новых аккаунтов Яндекс.Директ и настройки токенов.
- **Просмотр и управление кампаниями**: В разделе "Ставки" и "Стратегии" доступны данные о кампаниях, ставки и настройки стратегий.
- **Анализ данных**: Раздел "Статистика" включает таблицы и графики для анализа данных по выбранным кампаниям.
- **Настройка графика и временных интервалов**: На главной странице выберите временной интервал и примените индикаторы для анализа графика.

### Экспорт данных
- Данные могут быть экспортированы в формат Excel (CSV) из раздела "Статистика" с помощью кнопки "Экспортировать".

## Разработка

### Основные библиотеки и инструменты

- **Electron**: для создания кросс-платформенного интерфейса.
- **React или Vue** (по желанию): для управления состоянием и компонентами в интерфейсе.
- **Java**: для основной бизнес-логики и интеграции с API.
- **TradingView Charting Library**: для отображения профессиональных графиков.
- **PostgreSQL**: для хранения данных о кампаниях и пользователях.
- **Apache POI**: для экспорта данных в Excel.
- **JFreeChart**: для построения графиков статистики (в Java).
