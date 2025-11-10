# 第7回 Webエンジニアリング演習 レポート
## 4723122

## PUTリクエスト検証用のモデルとAPI部分のコード
```
class TodoItemPUT(BaseModel):
    title: str #やることのタイトル
    description: Optional[str] = None #やることの詳細説明
    completed: bool = False #完了状態
```
```
@app.put("/todos/{todo_id}")
def update_todo(todo_id: int, req: TodoItemPUT):#req:~ でJSONを変換して受け取る
    for i, todo in enumerate(todos):
        if todo.id == todo_id:
            todo.title = req.title
            todo.description = req.description
            todo.completed = req.completed
            return todo
    raise HTTPException(status_code=404, detail=f"ID{todo_id}が見つかりません")
```

## 動作確認

正常系：
```
curl -X 'PUT' \
  'http://127.0.0.1:8000/todos/2' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "title": "string",
  "description": "string",
  "completed": false
}'
```
```
{
  "id": 2,
  "title": "string",
  "description": "string",
  "completed": false
}
```

異常系：
```
curl -X 'PUT' \
  'http://127.0.0.1:8000/todos/1000' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "title": "string",
  "description": "string",
  "completed": false
}'
```
```
{
  "detail": "ID1000が見つかりません"
}
```



