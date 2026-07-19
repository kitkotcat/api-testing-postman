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
│   └── skillbox-api-testing.postman_collection.json
└── README.md
```

## How to run

1. Clone the repository.
2. Open Postman and select **Import**.
3. Import:

   `postman/skillbox-api-testing.postman_collection.json`

4. Create a Postman environment with these variables:

| Variable | Description |
|---|---|
| `base_url` | Base URL of the tested API |
| `api_username` | API username |
| `api_password` | API password |

5. Select the environment.
6. Update resource IDs when required.
7. Run individual requests or use Collection Runner.

## Security

Real credentials, passwords and tokens are not stored in this repository.

The collection uses:

- `{{base_url}}`
- `{{api_username}}`
- `{{api_password}}`

The request `PUT-NEG-01 — Без авторизации` explicitly uses `noauth` so that only the authorization behavior is tested.

## Planned improvements

- add Postman checks with `pm.test`;
- validate status codes and response schemas;
- add an example environment without secrets;
- add test cases and bug reports;
- replace hardcoded resource IDs with variables.

## Author

Ekaterina Peshkun  
Junior Manual QA Engineer
