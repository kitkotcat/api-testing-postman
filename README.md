# Тестирование REST API в Postman

Портфолио-проект по ручному тестированию REST API в **Postman**.

В репозитории собрана коллекция из **18 запросов**, покрывающих позитивные, негативные, граничные сценарии, авторизацию, валидацию и базовые security-проверки.

## Что проверяется

- обновление товаров через `PUT`;
- удаление товаров через `DELETE`;
- проверка остатков товаров;
- регистрация пользователя;
- проверка данных через API endpoints.

## Покрытие тестами

- обновление товара валидными данными;
- некорректные типы данных;
- пустое тело запроса;
- граничное значение `price = 0`;
- запросы без авторизации;
- несуществующие ID ресурсов;
- успешное и повторное удаление;
- удаление без ID;
- базовые SQL injection inputs;
- проверка остатков товара.

## Инструменты и технологии

- Postman;
- REST API;
- HTTP: `GET`, `POST`, `PUT`, `DELETE`;
- JSON;
- Basic Auth;
- Environment Variables;
- Git / GitHub.

## Тестовая документация

- [Матрица API-сценариев](docs/api-test-scenarios.md) — 18 сценариев из Postman Collection с методами, endpoints, авторизацией и типами request body.
- [Тест-кейсы и баг-репорты](docs/manual-test-artifacts/product-creation-api-test-cases-and-bug-reports.xlsx) — позитивные и негативные сценарии создания товара, Expected / Actual Result, Severity, Priority и связанные дефекты.

## Структура репозитория

```text
api-testing-postman/
├── postman/
│   ├── skillbox-api-testing.postman_collection.json
│   └── skillbox-api-testing.example.postman_environment.json
├── docs/
│   ├── api-test-scenarios.md
│   └── manual-test-artifacts/
│       └── product-creation-api-test-cases-and-bug-reports.xlsx
├── .gitignore
└── README.md
```

## Как запустить

1. Клонировать репозиторий.
2. Открыть Postman и выбрать **Import**.
3. Импортировать коллекцию:
   `postman/skillbox-api-testing.postman_collection.json`
4. Импортировать пример окружения:
   `postman/skillbox-api-testing.example.postman_environment.json`
5. Скопировать или отредактировать импортированное окружение.
6. Заменить placeholder-значения на данные тестируемого API.

| Переменная | Назначение |
|---|---|
| `base_url` | Базовый URL тестируемого API |
| `api_username` | Имя пользователя API |
| `api_password` | Пароль API |
| `product_id` | ID существующего товара |
| `missing_product_id` | ID несуществующего товара |

7. Выбрать окружение.
8. Запускать запросы вручную или через **Postman Collection Runner**.

Пример окружения содержит только placeholders. Реальные credentials в репозиторий не добавляются.

## Автоматические проверки в Postman

На уровне коллекции добавлены проверки, которые:

- фиксируют неожиданные серверные ошибки `5xx`;
- проверяют возможность распарсить response, если `Content-Type` указывает на JSON.

Проверки конкретных status codes и response schemas добавляются только там, где подтверждены Expected Result или API contract.

## Безопасность

Реальные логины, пароли и токены в репозитории не хранятся.

Коллекция использует переменные:

- `{{base_url}}`
- `{{api_username}}`
- `{{api_password}}`

Запрос `PUT-NEG-01 — Без авторизации` использует `noauth`, чтобы отдельно проверить поведение API без авторизации.

## Что демонстрирует проект

- ручное тестирование REST API;
- позитивные и негативные сценарии;
- работа с HTTP и JSON;
- проверка авторизации и валидации;
- оформление тест-кейсов и баг-репортов;
- работа с переменными окружения Postman.

## Автор

**Екатерина Пешкун**
Junior QA Engineer
