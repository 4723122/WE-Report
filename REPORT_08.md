# 第8回 Webエンジニアリング演習 レポート
## 4723122

## 実装した内容
@app.put("/todos/{todo_id}")
async def update_todo(todo_id: int, req: TodoItemUpdate_Pydantic):
    todo = await TodoItem.get(id=todo_id)
    if todo:
        todo.title = req.title
        todo.description = req.description
        todo.completed = req.completed
        await todo.save()
        return todo
    else:
        raise HTTPException(status_code=404, detail=f"ID{todo_id}が見つかりません")


##動作確認結果

正常系
```
curl -X 'PUT' \
  'http://127.0.0.1:8000/todos/1' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "title": "sssss",
  "description": "string",
  "completed": false
}'
```
```
{
  "title": "sssss",
  "description": "string",
  "completed": false
}
```


存在しないID
```
curl -X 'PUT' \
  'http://127.0.0.1:8000/todos/100' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "title": "ELSE",
  "description": "string",
  "completed": false
}'
```
```
{
  "detail": "Object \"TodoItem\" does not exist"
}
```