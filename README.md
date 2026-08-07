# coverage-verification-service

coverage-verification-service — domain: insurance

- **Port:** 8802
- **Language:** Python 3.11 + Flask
- **Database:** `insurance` (Postgres, table `coverage_verification`)
- **Event bus:** Kafka

## API

| Method    | Path                       |
|-----------|----------------------------|
| GET       | `/api/coverage_verification/`          |
| POST      | `/api/coverage_verification/`          |
| GET       | `/api/coverage_verification/<id>`      |
| PUT/PATCH | `/api/coverage_verification/<id>`      |
| DELETE    | `/api/coverage_verification/<id>`      |
| GET       | `/health`                  |
| GET       | `/ready`                   |

## Events

**Publishes:** (none)
**Subscribes:** (none)

## HTTP peer dependencies

- `eligibility-service`
- `patients-service`
- `audit-log-service`

## Local dev

```bash
pip install -e ../../libs/py-healthcare-common
pip install -r requirements.txt
cp .env.example .env
(cd ../../infra && docker compose up -d postgres kafka kafka-init)
python -m app.main
```

## Tests

```bash
pytest
```
