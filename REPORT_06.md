# 第6回　Webエンジニアリング演習 レポート
## 4723122

## 動作確認
curl -X 'GET' \
  'http://127.0.0.1:8000/todos?query=%E7%89%9B%E4%B9%B3' \
  -H 'accept: application/json'


[
  {
    "id": 1,
    "title": "牛乳とパンを買う",
    "description": "牛乳は低温殺菌じゃないとだめ",
    "completed": false
  },
  {
    "id": 1,
    "title": "牛乳とパンを買う",
    "description": "牛乳は低温殺菌じゃないとだめ",
    "completed": false
  }
]