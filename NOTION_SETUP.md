# Notion — пошаговая настройка базы знаний

## Что получится

```
Biotech Research Hub (Notion-страница)
├── 🧬 Knowledge Base    ← все MD-карточки (GEN, CMP, PWY, ENZ, ORG...)
├── 📋 Research Plan     ← задачи/эксперименты, связанные с карточками KB
└── 📝 Conclusions       ← выводы, связанные с задачами и карточками KB
```

Базы связаны отношениями (relations): из задачи плана можно кликнуть
на карточку GEN-001, из вывода — вернуться к задаче.

---

## Шаг 1 — Создай Notion-аккаунт

Если аккаунта нет: https://www.notion.so/signup  
Бесплатный план достаточен (лимит 1000 блоков снят для личных страниц).

---

## Шаг 2 — Создай интеграцию (API-ключ)

1. Открой https://www.notion.so/my-integrations
2. Нажми **"+ New integration"**
3. Заполни:
   - Name: `Biotech Importer`
   - Type: **Internal**
   - Workspace: выбери свой workspace
4. Нажми **Submit**
5. Скопируй **Internal Integration Token** (начинается с `secret_...`)  
   → Это и есть `NOTION_TOKEN` для скриптов

---

## Шаг 3 — Создай родительскую страницу в Notion

1. В Notion нажми **"+ New page"** в левой панели
2. Назови её: `Biotech Research`  
   (или любое другое название)
3. Нажми **"..."** → **"Add connections"** → выбери `Biotech Importer`
4. Скопируй ID страницы из URL:
   ```
   https://notion.so/Biotech-Research-abcdef1234567890abcdef1234567890
                                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
                                       это и есть PARENT_PAGE_ID (32 символа)
   ```
   ID без тире, 32 символа. Если в URL есть тире — убери их.

---

## Шаг 4 — Установи зависимости Python

Открой терминал (PowerShell или cmd) и выполни:

```powershell
pip install notion-client pyyaml
```

---

## Шаг 5 — Настрой `notion_import.py`

Открой файл `notion_import.py` и замени три строки вверху:

```python
NOTION_TOKEN   = "secret_ВАШ_ТОКЕН_СЮДА"      # ← вставь токен из шага 2
PARENT_PAGE_ID = "ВАШ_ID_СТРАНИЦЫ_СЮДА"        # ← вставь ID из шага 3
BIOTECH_DIR    = r"A:\job\biotech"             # ← оставь как есть
```

---

## Шаг 6 — Запусти импорт

```powershell
cd A:\job\biotech
python notion_import.py
```

Импорт займёт 1–3 минуты (throttling API ~3 req/s).  
В конце скрипт напечатает **ID базы Knowledge Base** — сохрани его.

Пример вывода:
```
📡 Проверяю подключение к Notion...
   ✓ Подключено как: John
📊 Создаю базу данных Knowledge Base...
   ✓ База создана (ID: abc123...)
   ...
✅  Импортировано: 47
📋 ID базы для следующего шага: abc123def456...
```

---

## Шаг 7 — Создай Research Plan и Conclusions

Открой `notion_research_plan.py` и замени три строки:

```python
NOTION_TOKEN      = "secret_ВАШ_ТОКЕН_СЮДА"
PARENT_PAGE_ID    = "ВАШ_ID_СТРАНИЦЫ_СЮДА"      # ← та же страница
KB_DATABASE_ID    = "ID_БАЗЫ_ИЗ_notion_import"  # ← напечатан в шаге 6
```

Запусти:

```powershell
python notion_research_plan.py
```

---

## Шаг 8 — Шаринг

Чтобы дать доступ коллеге:

1. Открой страницу `Biotech Research` в Notion
2. Нажми **"Share"** (правый верхний угол)
3. Введи email коллеги → выбери уровень доступа:
   - **Can edit** — может редактировать карточки и план
   - **Can comment** — только комментарии
   - **Can view** — только просмотр
4. Или нажми **"Copy link"** для публичного доступа (только просмотр)

---

## Как пользоваться базой

### Поиск по параметрам

В базе Knowledge Base нажми **"Filter"**:

| Хочу найти | Фильтр |
|------------|--------|
| Все генные модификации | Type = gene_modification |
| Только Y. lipolytica | Organism = yarrowia_lipolytica |
| Высокая уверенность | Confidence = high |
| Всё по CBGVA | Target Compound contains CBGVA |
| Комбинация | Type = compound AND Confidence = high |

Сохрани часто используемые фильтры как **Views** (кнопка "Add a view").

### Поиск по тексту

В правом верхнем углу базы → иконка поиска (🔍) → ищет по телу карточек.

### Research Plan

- Создай новую задачу через **"+ New"**
- В поле **"Knowledge Base"** выбери связанные карточки из KB
- Обнови **Status** по мере выполнения
- После завершения — создай запись в **Conclusions** и свяжи с задачей

### Полезные Views (создай вручную)

- **По типу** — Group by: Type
- **По соединению** — Group by: Target Compound  
- **Только непроверенное** — Filter: Confidence = low
- **Активные задачи** — (в Research Plan) Filter: Status = "В работе"

---

## Обновление базы

Если добавил новые MD-карточки — просто запусти `notion_import.py` снова.  
Новые карточки добавятся; старые НЕ задублируются (у них другой Title/ID).

---

## Возможные ошибки

| Ошибка | Причина | Решение |
|--------|---------|---------|
| `object_not_found` | Страница не расшарена с интеграцией | Шаг 3: Add connections |
| `unauthorized` | Неверный токен | Проверь NOTION_TOKEN |
| `validation_error` | Неверный ID страницы | ID — 32 символа без тире |
| `rate_limited` | Слишком частые запросы | Скрипт уже делает паузы; подожди |
