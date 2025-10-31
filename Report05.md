# 第5回 Webエンジニアリング演習　レポート
## 4723122

## 各エンドポイントでのSwagger UIでのテスト結果
### GET /
Request 1:
```
curl -X 'GET' \
  'http://localhost:8000/' \
  -H 'accept: application/json'
```
Reaponse 1:
```
{
  "Hello": "World"
}
```


Request 2:
```
curl -X 'GET' \
  'http://localhost:8000/health' \
  -H 'accept: application/json'
```
Response 2:
```
{
  "status": "healthy"
}
```


Request 3:
```
curl -X 'GET' \
  'http://localhost:8000/items/2' \
  -H 'accept: application/json'
```
Response 3:
```
{
  "item_id": 2
}
```


Request 4:
```
curl -X 'GET' \
  'http://localhost:8000/items/0' \
  -H 'accept: application/json'
```
Response 4:
```
{
  "detail": "item_id must be positive"
}
```
