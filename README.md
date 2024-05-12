# Проект: Анализ Зарплат в IT-Индустрии

## Описание проекта

Целью данного проекта было проведение углубленного анализа данных о зарплатах в IT-индустрии. В рамках исследования были выполнены этапы предобработки данных, разведочного анализа (EDA), очистки данных от выбросов и построения предсказательных моделей. В результате проекта были выявлены ключевые тенденции и предложены рекомендации для дальнейшего использования данных.

## Структура проекта

### 1. Импорт данных и начальная обработка
- **Загрузка данных**: Датасет `ds_salaries.csv`, содержащий информацию о годах работы, уровне опыта, типе занятости, должностях, зарплатах в разных валютах, размере компании и удаленности работы.
- **Проверка структуры и типов данных**: Выявлено, что датасет состоит из 3755 записей и 11 столбцов с числовыми и категориальными переменными.
- **Удаление дубликатов**: Обнаружено и удалено 1171 дубликатов, итоговый размер датасета составил 2584 записи.
- **Проверка пропусков**: Пропущенные значения отсутствуют.

### 2. Разведочный анализ данных (EDA)
- **Общая статистика и описательный анализ**:
  - **work_year**: Диапазон от 2020 до 2023 года
  - **salary_in_usd**: Средняя зарплата около $137570 с разбросом до $450000
  - **remote_ratio**: Преобладание полностью удаленной и офисной работы (0% и 100%)

- **Распределение числовых переменных**:
  - Построены гистограммы и боксплоты для `salary_in_usd`, `remote_ratio` и `work_year`

- **Анализ категориальных переменных**:
  - Наиболее частые уровни опыта: `SE` (Senior) и `MI` (Mid-level)
  - Преобладание полной занятости (`FT`)
  - Основные должности: `Data Engineer`, `Data Scientist`
  - Валюта зарплат: преимущественно `USD`
  - Основное местоположение сотрудников и компаний: США
  - Размеры компаний: в основном средние (`M`)

### 3. Визуализация данных
- **Тепловая карта (Heatmap)**: Показала слабую корреляцию между числовыми переменными
- **Гистограммы и боксплоты**: Использованы для анализа распределения зарплат и удаленности работы

### 4. Углубленный анализ
- **Зарплаты по категориям**:
  - Детализированный анализ по уровням опыта, типу занятости и должностям показал значительные различия в распределении зарплат

- **Влияние удаленной работы**:
  - Полностью удаленные позиции имеют более широкий диапазон зарплат
  - Senior и Mid-level позиции чаще бывают полностью удаленными

- **Влияние размера компании**:
  - Средние компании (`M`) предоставляют более широкий диапазон зарплат по сравнению с малыми и крупными компаниями

### 5. Очистка данных
- **Идентификация и обработка выбросов**:
  - Применен метод межквартильного размаха (IQR Method) для удаления выбросов по каждой категории опыта и типа занятости
  - **Winsorization**: Рассмотрен как альтернативный метод для сглаживания выбросов

## Рекомендации и выводы
- **Очистка данных**:
  - Рекомендуется проводить отдельную очистку по категориям опыта, типам занятости и должностям для повышения точности анализа
  
- **Дополнительный анализ**:
  - Изучение дополнительных факторов, таких как образование, отрасль и географическое расположение, может значительно улучшить качество предсказаний


## Используемые библиотеки
- `pandas`
- `matplotlib`
- `seaborn`
