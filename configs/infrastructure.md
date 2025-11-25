# Infrastructure Reference

## n8n (Northflank)

- **URL:** https://annoris--n8n-make--xjvz9xynmzwk.code.run
- **Gateway Workflow ID:** JF3f6gGYZhEyv6U4
- **Webhook:** /webhook/make-gateway-v2

## Make.com

- **Token:** 1093fee2-60e0-4432-8c6c-205c5706cb6c
- **Team ID:** 2552758
- **Org ID:** 5038858
- **Region:** EU2
- **Base URL:** https://eu2.make.com/api/v2

## Gateway 10 Actions

| Action | Method | Endpoint |
|--------|--------|----------|
| list | GET | /scenarios?organizationId=5038858 |
| get | GET | /scenarios/{id} |
| create | POST | /scenarios?confirmed=true |
| update | PATCH | /scenarios/{id} |
| delete | DELETE | /scenarios/{id} |
| run | POST | /scenarios/{id}/run |
| start | POST | /scenarios/{id}/start |
| stop | POST | /scenarios/{id}/stop |
| clone | POST | /scenarios/{id}/clone |
| logs | GET | /scenarios/{id}/logs |

## Critical API Notes

### n8n Switch node v3
```json
"conditions": {
  "options": {
    "version": 1,
    "caseSensitive": true,
    "typeValidation": "strict"
  },
  "combinator": "and",
  "conditions": [...]
}
```
Без этих полей rules игнорируются!

### Make.com Create Scenario
- `blueprint` = JSON.stringify() — СТРОКА
- `scheduling` = JSON.stringify() — СТРОКА
- `teamId` в body ОБЯЗАТЕЛЕН
- `flow: []` для пустого сценария
