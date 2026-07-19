# REST API Testing with Postman

Portfolio project demonstrating manual REST API testing in Postman.

## Project overview

The collection contains **18 requests** covering positive, negative, boundary, authorization, validation and basic security scenarios.

Main areas:

- product updates with `PUT`;
- product deletion with `DELETE`;
- product stock verification;
- user registration;
- data verification through API endpoints.

## Test coverage

- valid product updates;
- invalid data types;
- empty request bodies;
- boundary value `price = 0`;
- requests without authorization;
- non-existent resource IDs;
- successful and repeated deletion;
- deletion without an ID;
- basic SQL injection inputs;
- product stock checks.

## Tools and technologies

- Postman
- REST API
- HTTP: `GET`, `POST`, `PUT`, `DELETE`
- JSON
- Basic Auth
- Environment variables
- Git and GitHub

## Repository structure

```text
api-testing-postman/
├── postman/
│   ├── skillbox-api-testing.postman_collection.json
│   └── skillbox-api-testing.example.postman_environment.json
├── .gitignore
└── README.md
```

## How to run

1. Clone the repository.
2. Open Postman and select **Import**.
3. Import the collection:

   `postman/skillbox-api-testing.postman_collection.json`

4. Import the example environment:

   `postman/skillbox-api-testing.example.postman_environment.json`

5. In Postman, duplicate or edit the imported environment.
6. Replace the placeholder values with values for the tested API:

   | Variable | Description |
   |---|---|
   | `base_url` | Base URL of the tested API |
   | `api_username` | API username |
   | `api_password` | API password |
   | `product_id` | ID of an existing product |
   | `missing_product_id` | ID of a non-existent product |

7. Select the environment.
8. Run individual requests or use Postman Collection Runner.

The example environment contains placeholders only. Real credentials must not be committed to the repository.

## Automated checks

The collection includes collection-level Postman checks that:

- fail when an API request returns an unexpected `5xx` server error;
- verify that a response can be parsed when its `Content-Type` declares JSON.

Request-specific status code and response schema checks are added only when verified expected results or an API contract are available.

## Security

Real credentials, passwords and tokens are not stored in this repository.

The collection uses:

- `{{base_url}}`
- `{{api_username}}`
- `{{api_password}}`

The request `PUT-NEG-01 — Без авторизации` explicitly uses `noauth` so that only the authorization behavior is tested.

## Planned improvements

- validate status codes and response schemas;
- add test cases and bug reports;
- replace hardcoded resource IDs with variables.

## Author

Ekaterina Peshkun  
Junior Manual QA Engineer
