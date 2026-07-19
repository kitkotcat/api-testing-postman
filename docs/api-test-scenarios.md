# API Test Scenario Matrix

This document is generated from the Postman collection stored in the repository.

## Purpose

The matrix provides a readable overview of the API scenarios covered by the collection.

It documents:

- request identifiers and scenario names;
- HTTP methods and endpoints;
- authentication requirements;
- request body types;
- current execution status;
- expected-result placeholders.

## Current automation

- A collection-level check fails when an unexpected `5xx` response is returned.
- JSON parsing is validated when the response `Content-Type` declares JSON.
- Request-specific status codes and schemas are not asserted without verified requirements.

## Assumptions and limitations

- The repository does not currently contain an authoritative API contract.
- The collection does not contain saved response examples.
- Expected HTTP status codes must be verified against requirements or actual API behaviour.
- Execution status is set to `Not run` because the example environment contains placeholders.

## Scenario summary

- Total scenarios: **18**
- Methods: **DELETE — 5**, **GET — 3**, **POST — 1**, **PUT — 9**
- Scenario types: **Authentication — 1**, **Diagnostic — 1**, **Integration — 2**, **Negative — 10**, **Positive — 4**

## Test scenarios

| ID | Group | Type | Scenario | Method | Endpoint | Authentication | Body | Expected status | Execution |
|---|---|---|---|---|---|---|---|---|---|
| `PUT-NEG-01` | PUT | Negative | PUT-NEG-01 — Без авторизации | `PUT` | `{{base_url}}/products/{{product_id}}` | No authentication | JSON | To verify against API contract | Not run |
| `PUT-NEG-03` | PUT | Negative | PUT-NEG-03 — Неверный тип данных | `PUT` | `{{base_url}}/products/{{product_id}}` | Inherited Basic Auth | JSON | To verify against API contract | Not run |
| `PUT-NEG-06` | PUT | Negative | PUT-NEG-06 — Запрос без body | `PUT` | `{{base_url}}/products/{{product_id}}` | Inherited Basic Auth | Empty raw body | To verify against API contract | Not run |
| `PUT-POS-02` | PUT | Positive | PUT-POS-02 — Полное обновление всех полей | `PUT` | `{{base_url}}/products/{{product_id}}` | Inherited Basic Auth | JSON | To verify against API contract | Not run |
| `PUT-POS-03` | PUT | Positive | PUT-POS-03 — Граничное значение (price = 0) | `PUT` | `{{base_url}}/products/{{product_id}}` | Inherited Basic Auth | JSON | To verify against API contract | Not run |
| `PUT-NEG-02` | PUT | Negative | PUT-NEG-02 — Пустое тело | `PUT` | `{{base_url}}/products/{{product_id}}` | Inherited Basic Auth | JSON | To verify against API contract | Not run |
| `PUT-POS-01` | PUT | Positive | PUT-POS-01 — Обновление товара (валидные данные) | `PUT` | `{{base_url}}/products/{{product_id}}` | Inherited Basic Auth | JSON | To verify against API contract | Not run |
| `PUT-NEG-05` | PUT | Negative | PUT-NEG-05 — SQL-инъекция | `PUT` | `{{base_url}}/products/{{product_id}}` | Inherited Basic Auth | JSON | To verify against API contract | Not run |
| `PUT-NEG-04` | PUT | Negative | PUT-NEG-04 — Несуществующий ID | `PUT` | `{{base_url}}/products/{{missing_product_id}}` | Inherited Basic Auth | JSON | To verify against API contract | Not run |
| `DEL-POS-01` | DELETE | Positive | DEL-POS-01 — Удаление существующего товара | `DELETE` | `{{base_url}}/products/{{product_id}}` | Inherited Basic Auth | Empty raw body | To verify against API contract | Not run |
| `DEL-NEG-04` | DELETE | Negative | DEL-NEG-04 — Повторное удаление | `DELETE` | `{{base_url}}/products/{{product_id}}` | Inherited Basic Auth | Empty raw body | To verify against API contract | Not run |
| `DEL-NEG-05` | DELETE | Negative | DEL-NEG-05 — Удаление без ID | `DELETE` | `{{base_url}}/products` | Inherited Basic Auth | Empty raw body | To verify against API contract | Not run |
| `DEL-NEG-06` | DELETE | Negative | DEL-NEG-06 — SQL-инъекция в ID | `DELETE` | `{{base_url}}/products/1%20OR%201%3D1` | Inherited Basic Auth | Empty raw body | To verify against API contract | Not run |
| `DEL-NEG-02` | DELETE | Negative | DEL-NEG-02 — Несуществующий ID | `DELETE` | `{{base_url}}/products/{{missing_product_id}}` | Inherited Basic Auth | Empty raw body | To verify against API contract | Not run |
| `TC-01` | Тестирование остатков товара | Integration | TC-01 Отображение корректного остатка товара (UI + API + DB) | `GET` | `{{base_url}}/products` | Inherited Basic Auth | None | To verify against API contract | Not run |
| `TC-02` | Тестирование остатков товара | Integration | TC-02 — Обновление остатка после заказа | `GET` | `{{base_url}}/orders` | Inherited Basic Auth | None | To verify against API contract | Not run |
| `AUTH-POST-01` | Тестирование остатков товара | Authentication | AUTH-POST-01 — Регистрация пользователя | `POST` | `{{base_url}}/register` | Inherited Basic Auth | JSON | To verify against API contract | Not run |
| `DEBUG-GET-01` | Тестирование остатков товара | Diagnostic | DEBUG-GET-01 — Проверка данных через debug endpoint | `GET` | `{{base_url}}/debug/db` | Inherited Basic Auth | None | To verify against API contract | Not run |

## Execution guidance

Before running the collection, import the example environment and replace all placeholder values.

After requirements are confirmed, update this document with:

- verified expected status codes;
- response schema expectations;
- actual execution results;
- links to confirmed defects;
- test execution date and environment.
