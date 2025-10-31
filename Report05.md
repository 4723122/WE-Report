# 第5回 Webエンジニアリング演習　レポート
## 4723122

## 各エンドポイントでのSwagger UIでのテスト結果
### GET /
Request:
```
curl -X 'GET' \
  'http://localhost:8000/' \
  -H 'accept: application/json'
```
Reaponse:
```
{
  "Hello": "World"
}
```


Request:
```
curl -X 'GET' \
  'http://localhost:8000/health' \
  -H 'accept: application/json'
```
Response:
```
{
  "status": "healthy"
}
```


Request:
```
curl -X 'GET' \
  'http://localhost:8000/items/2' \
  -H 'accept: application/json'
```
Response:
```
{
  "item_id": 2
}
```


Request:
```
curl -X 'GET' \
  'http://localhost:8000/items/0' \
  -H 'accept: application/json'
```

Request:
```
curl -X 'GET' \
  'http://localhost:8000/items/0' \
  -H 'accept: application/json'
```
Response:
```
{
  "detail": "item_id must be positive"
}
```
